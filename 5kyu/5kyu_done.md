### Rot13
def rot13(string)
  rot = string.chars.map do |ltr|
    if ltr.downcase.ord >= 97 && ltr.downcase.ord <= 122
      if ltr == ltr.downcase
        change = ltr.ord + 13  
        change > 122 ? (change-26).chr : change.chr
      else
        change = ltr.downcase.ord + 13  
        change > 122 ? (change-26).chr.upcase : change.chr.upcase
      end
    else
      ltr
    end
  end
  rot.join
end

