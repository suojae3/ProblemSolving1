
![header](https://capsule-render.vercel.app/api?type=waving&color=gradient&height=250&section=header&text=Problem%20Solving%20-mySolution&fontSize=40&animation=fadeIn&fontAlign=33&fontAlignY=40)


<br/>

---

### 01. JadenCase 문자열 만들기

&nbsp;&nbsp;&nbsp;&nbsp;<img src="image/1.png"><br/>


```Swift
func solution(_ s: String) -> String {
    var shouldCapitalize = true
    return s.lowercased().map { char -> String in
        if char == " " {
            shouldCapitalize = true
            return String(char)
        } else if shouldCapitalize {
            shouldCapitalize = false
            return String(char).uppercased()
        } else  {
            return String(char)
        }
    }.joined()
}
```

1. 음절(?)의 첫단어만 대문자로 바꿔주면 되기 때문에 flag를 통해 문자열을 바꿔준다.
2. 만약 문자열이 한 번 대문자로 바뀌면 flag를 false로 해줘서 나머지 문자열은 그냥 통과시킨다.
3. 빈문자열(띄어쓰기)가 오면 flag를 true로 바꿔준다.
4. String 이외의 같은 전부 마지막 else문을 통과시켜준다
