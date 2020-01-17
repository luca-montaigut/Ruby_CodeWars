#Vowel Count
def getCount(inputStr)
  inputStr.count("aeiou")
end


#Get the Middle Character
def get_middle(s)
  if s.size.odd?
    s[s.size/2]
  else
    s[s.size/2-1]+s[s.size/2]
  end
end


#Square Every Digit
def square_digits num
  num.to_s.split('').map{|i| i.to_i**2}.join.to_i
end


#Is this a triangle?
def isTriangle(a,b,c)
  tri = []
  tri << a
  tri << b
  tri << c
tri.max < tri.min(2).sum 
end

#Disemvowel Trolls
def disemvowel(str)
  str.delete"aAeEiIoOuU"
end

#Shortest Word
def find_short(s)
  l = s.split(" ").map.sort_by(&:size).first.size
end

#List Filtering
def filter_list(l)
  l.keep_if {|a| a!=a.to_s && a.to_s.count("0-9")>0}
end

#Credit Card Mask
def maskify(cc)
  i = 0
  finish = []
  four = cc.chars.last(4).join
  while i < cc.size-4
    finish << "#"
    i += 1
  end
  finish << four
  finish.join
end

#Jaden Casing Strings
class String
  def toJadenCase
    s = self.split
    str = s.map{|x| x.capitalize}.join(" ")
  end
end

#Categorize New Member
def openOrSenior(data)
  cat = []
data.size.times do |i|
    if data[i][0] >= 55 && data[i][1] > 7
      cat << 'Senior'
    else
      cat << 'Open'
    end
  end
  return cat
end
