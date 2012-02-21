# What is the difference between a Procs, blocks, and lambdas?

This is my talk to the Feb 2012 YEGrb meetup where I answer the question, "What is the difference between a Proc, block and lambda?"

## Notes

 * "What are Procs, blocks and lambdas?"
 * Refine question
   - limiting to Ruby 1.9.2
 * They're all ways to capture and re-use a unit of code
 * Define the syntax for each
   * blocks
     * created using do..end or { ... }
     * invoked using yield
     * not an argument
     * it's syntax
   * Proc
     * created using Proc.new or proc
     * invoked using Proc#call
   * lambda
     * created using lambda or ->(a,b) (stabby)
     * invoked using #call
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