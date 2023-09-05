# Ruby Gym: Leap Year

This program should:
  - Take a year (Say 2016)
  - Determine if the given year is a leap year
  - If the given year is a leap year print, 
    ```
    "2016 is a leap year!"
    ```
  
  - Otherwise print, 
    ```
    "2015 is not a leap year."
    ```

Hint: To determine whether a year is a leap year, follow these steps:

1. If the year is divisible by 4, go to step 2. Otherwise, go to step 5.
2. If the year is divisible by 100, go to step 3. Otherwise, go to step 4.
3. If the year is divisible by 400, go to step 4. Otherwise, go to step 5.
4. The year is a leap year (it has 366 days).
5. The year is not a leap year (it has 365 days).


```ruby
years = [
  1700,
  1940,
  2038
]
year = years.sample
# write your program below
```
{: .repl #leap_year title="Leap Year" readonly_lines="[1,2,3,4,5,6,7]"}


```ruby
describe "Leap Year" do
  it "prints '2016 is a leap year!' if the year is 2016" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Array).to receive(:sample).and_return(2016)
    output = capture_stdout { require_relative(path) }
    expect(output).to match(/2016 is a leap year!/), "Expected output to be '2016 is a leap year!', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #leap_year_test_1 for="leap_year" title="Leap Year prints '2016 is a leap year!' if the year is 2016" points="1"}


```ruby
describe "Leap Year" do
  it "prints '1804 is a leap year!' if the year is 1804" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Array).to receive(:sample).and_return(1804)
    output = capture_stdout { require_relative(path) }
    expect(output).to match(/1804 is a leap year!/), "Expected output to be '1804 is a leap year!', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #leap_year_test_2 for="leap_year" title="Leap Year prints '1804 is a leap year!' if the year is 1804" points="1"}


```ruby
describe "Leap Year" do
  it "prints '1800 is not a leap year.' if the year is 1800" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Array).to receive(:sample).and_return(1800)
    output = capture_stdout { require_relative(path) }
    expect(output).to match(/1800 is not a leap year./), "Expected output to be '1800 is not a leap year.', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #leap_year_test_3 for="leap_year" title="Leap Year prints '1800 is not a leap year.' if the year is 1800" points="1"}


```ruby
describe "Leap Year" do
  it "prints '2200 is not a leap year.' if the year is 2200" do
    path = "/tmp/code.rb"
    allow_any_instance_of(Array).to receive(:sample).and_return(2200)
    output = capture_stdout { require_relative(path) }
    expect(output).to match(/2200 is not a leap year./), "Expected output to be '2200 is not a leap year.', but was '#{output}'."
  end

  def capture_stdout
    old_stdout = $stdout
    $stdout = StringIO.new
    yield
    $stdout.string
  ensure
    $stdout = old_stdout
  end
end
```
{: .repl-test #leap_year_test_4 for="leap_year" title="Leap Year prints '2200 is not a leap year.' if the year is 2200" points="1"}
