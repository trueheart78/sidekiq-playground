# Sidekiq Playground

## Running the Server

Make sure redis is running in the background. You may need to run
`redis-server` if it is not.

### Run the Sidekiq Server

```sh
bundle exec sidekiq -r ./worker.rb
```

## Running the Sidekiq Client

```sh
bundle exec -r ./worker.rb
```

Now you can send commands to be performed.

```ruby
OurWorker.perform_async 'hard'
OurWorker.perform_async 'super hard'
```

You can also send _when_ they should be performed

```ruby
OurWorker.perform_in 5, 'hard'
```
