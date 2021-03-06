idris-unicode
-------------

[![Build Status](https://travis-ci.org/Heather/idris-unicode.png?branch=master)](https://travis-ci.org/Heather/idris-unicode)
[![Twitter][]](http://www.twitter.com/Cynede)

[There are several reasons why idris will not support unicode operators](https://github.com/idris-lang/Idris-dev/wiki/Unofficial-FAQ#will-there-be-support-for-unicode-characters-for-operators)

This project is to discover possible ways of using them in Idris <br/>
Contributions are very welcome!

 - basic (sane) module to include is `Control.Unicode`
 - include `Unicode` with random unicode extras (dangerous and not recommended for now)

Simple example
--------------

``` idris
prog : String
prog = "+ + * - /"

ℚ : Type
ℚ = if '/' ∈ (፨ prog)
            then ℝ
            else ℤ

main : ໒ ()
main = putStrLn $ "The program "
                  ++ prog
                  ++ " calculates the value "
                  ++ (show $ acc (፨ prog) 0)
 where acc : (List Char) → (ℚ) → (ℚ)
       acc [] m = m
       acc (x::xs) m = acc xs $ case x of
                                 '+' => m + 1
                                 '-' => m - 1
                                 '*' => m ⋅ 2
                                 '/' => m ÷ 2
                                 _   => m
```

[Twitter]: http://mxtoolbox.com/Public/images/twitter-icon.png
