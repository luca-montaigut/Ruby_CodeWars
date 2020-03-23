#Find The Parity Outlier
def find_outlier(integers)
  if integers.count{|x| x.odd?} > 1
    return integers.select(&:even?).join().to_i
  else
    return integers.select(&:odd?).join().to_i
  end
end

### Playing with digits
def dig_pow(n, p)
  num = 0
  n.digits.reverse.each_with_index { |n, i| num = num + n**(p + i) } 
  num/n > 0 && num/n == num.to_f/n.to_f ? num/n : -1
end

### Build Tower
def towerBuilder(n_floors)
  pyramid = []
  i = 1
    while i / 2 != (n_floors) 
      if i % 2 != 0
      pyramid << " " * ((n_floors - i/2)-1) + "*" * i + " " * ((n_floors- i/2)-1)
      end
    i += 1
    end
  return pyramid
end


### Array Helper
class Array
  def square
    self.map{ |x| x**2 } 
  end
  
  def cube
    self.map { |x| x**3 }
  end
  
  def average
    self.inject(:+)/self.size
  end
  
  def sum
    self.inject(:+)
  end
  
  def even
    self.map{ |x| x.even? ? x : nil }.compact
  end

  def odd
    self.map{ |x| x.odd? ? x : nil }.compact
  end
  
end


### Multi-tap Keypad Text Entry on an Old Mobile Phone
def presses(phrase)
  touch1 = [" ","A","D","G","J","M","P","T","W","*","#", "1"]
  touch2 = ["B","E","H","K","N","Q","U","X", "0"]
  touch3 = ["C","F","I","L","O","R","V","Y"]
  touch4 = ["S","Z", "2", "3", "4", "5", "6", "8"]
  touch5 = ["7", "9"]
  all = [touch1, touch2, touch3, touch4, touch5]
  sum = 0
  phrase.upcase.chars.each do |letter|
    i = 1
    all.each do |touch|
      sum += i if touch.include?(letter)
      i +=1
    end
  end
  return sum
end

### +1 Array
def up_array(arr)
  (arr.join.to_i+1).to_s.chars.map{ |nb| nb.to_i} unless arr == [] || arr.any?(&:negative?) || arr.sort.last >= 10
end
