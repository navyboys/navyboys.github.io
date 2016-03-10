---
layout: post
title: Continious Delivery with CircleCI
date: 2015-11-06 7:55
comments: true
categories: rails, deployment
keywords: CI CD
description: 
---

{% codeblock lang:ruby app/mailers/app_mailer.rb %}
class AppMailer < ActionMailer::Base
  def send_email(user)
    @user = user
    mail to: user.email, from: 'info@example.com', subject: 'Welcome to example.com'
  end
end
{% endcodeblock %}
