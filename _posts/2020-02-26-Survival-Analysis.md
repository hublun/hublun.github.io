---
layout: post
title: Survival Analysis with Stan
subtitle: Time to Event with Censorship
cover-img: /assets/img/path.jpg
thumbnail-img: /assets/img/prior_pc.png
share-img: /assets/img/path.jpg
tags: [biostats]
---
![Survival Curve](/assets/img/thumb.png){: .mx-auto.d-block :}

[Survival analysis in Stan](https://fsdias.github.io/survival_analysis/)

{% highlight javascript linenos %}
data{
  int N;
  int<lower=1,upper=3>N_group;
  vector[N] time;
  vector[N] weight;
  array[N] int<lower=0,upper=1>event;
  array[N] int<lower=1,upper=3>group_id;
}
parameters{
  real a;
  vector[N_group] a_group;
  vector[N_group] b_group;
  real<lower=0> k;
}
transformed parameters{
  
  vector[N] mu=exp(a+a_group[group_id]+b_group[group_id].*weight);
  vector[N] lambda= mu / tgamma(1 + 1 /k);
}
model{
   //Likelihood
  for (i in 1:N)
  if ( event[i] == 1 ) time[i] ~ weibull(k, lambda[i]);
    else target += weibull_lccdf(time[i] | k, lambda[i]);
  //Priors
  a~normal(0,1);
  a_group~normal(0,1);
  b_group~normal(0,1);
  k ~ gamma(2, 0.5);
}
generated quantities{
  vector[N] pred;
  for(i in 1:N){
    pred[i]=weibull_rng(k,lambda[i]);
}
}
{% endhighlight %}

![Survival Curve](/assets/img/surv0.png){: .mx-auto.d-block :}
