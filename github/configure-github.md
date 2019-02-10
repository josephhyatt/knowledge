# Configure Github

## Configuring Git

> We'll be using Git for our version control system so we're going to set it up to match our Github account. If you don't already have a Github account, make sure to [register](https://github.com/). It will come in handy for the future.

> Replace my name and email address in the following steps with the ones you used for your Github account.

```ruby
git config --global color.ui true
git config --global user.name "YOUR NAME"
git config --global user.email "YOUR@EMAIL.com"
ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"
```

> The next step is to take the newly generated SSH key and add it to your Github account. You want to copy and paste the output of the following command and [paste it here](https://github.com/settings/ssh).

```ruby
cat ~/.ssh/id_rsa.pub
```

> Once you've done this, you can check and see if it worked:

```ruby
ssh -T git@github.com
```

> You should get a message like this:

```ruby
Hi <github username>! You've successfully authenticated, but GitHub does not provide shell access.
```

