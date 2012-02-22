# What is the difference between a Procs, blocks, and lambdas?

This is my talk to the Feb 2012 YEGrb meetup where I answer the question, "What is the difference between a Proc, block and lambda?"

## Notes

 * "What are Procs, blocks and lambdas?"
 * Refine question
   - limiting to Ruby 1.9.2
 * They're all ways to capture and re-use a unit of code
 * Define the syntax for each
   * blocks

    [1, 2, 3].each do |a|
      puts a
    end
    
    [1, 2, 3].each { |a| puts a }

     * created using do..end or { ... }
     * invoked using yield
     * not an argument
     * it's syntax
     
   * Proc

    p = Proc.new do |a|
      puts a
    end
    
    p.call("Hello!")
    
    p = proc { |a| puts a }
    
    p.call("Bonjour!")
    
   * lambda

    l = lambda { |a| puts a }
    l.call('Voila')
    
    l = ->(a) { puts a }
    l.call("moshi moshi")
    
 * Talk about what is the same
   * they all create a closure
     - capture the variables that were defined at the time the block, proc or lambda was defined

 * Talk about what is different
   - procs and lambdas are objects, but a block is syntax
   - procs and lambdas are invoked with call, but a block is invoked with yield
   - proc and lambda differ in how control statements are handled
     * return values from lambda
     * don't call return from Proc, only works inside defining closure
   - proc and lambda differ in how arguments are handled
     * procs accept missing values, lambda's are stricter

 * When do I use them
   - when doing functional programming
     - your code becomes part of your application
   - when you re-use the same "wrapper" around different guts
   - to replace almost everything else in Ruby
   - other examples?

## Resources

 * http://www.youtube.com/watch?v=VBC-G6hahWA
 * http://experthuman.com/programming-with-nothing
 * http://techspry.com/ruby_and_rails/proc-and-lambda-in-ruby/