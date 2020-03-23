#Multiply
def multiply(a, b)
  a * b
end

#Sum of positive
def positive_sum(arr)
  arr.reject{|x| x <= 0 }.sum
end

#Century From Year
def century(year)
  (year - 1) / 100 + 1
end

#Grasshopper - Grade book
def get_grade(s1, s2, s3)
  score = (s1 + s2 + s3)/3
  if score >= 90
    return 'A'
  elsif score < 90 && score >= 80
    return 'B'
  elsif score < 80 && score >= 70
    return 'C'
  elsif score < 70 && score >= 60
    return 'D'
  else
    return 'F'
  end
end

