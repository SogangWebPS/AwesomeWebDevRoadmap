# HTML form과 유효성 검사

## Form

### Form 이란?

> 사용자가 정보를 입력 / 선택할 때 사용하는 `HTML Tag` 입니다.
- 사용자가 웹 사이트에 정보를 전송하는 것을 허용합니다.
    - 👉 text field, button field, select field 등의 역할을 수행합니다.

- 하지만 UX 관점에서 Form이 적을수록 더 좋으므로 꼭 필요할 때에만 Form을 사용합시다.

---

### Form의 기본 형태

> 기본 형태는 다음과 같습니다.

```html
<form action="/my-handling-form-page" method="post">
	...
</form>
```

- <form> 태그의 속성은 다양하게 존재합니다.

- [HTML 폼 구성 방법 | MDN](https://developer.mozilla.org/ko/docs/Learn/Forms/How_to_structure_a_web_form)

---

### `<label>`, `<input>`, `<textarea>`

```html
<form action="/my-handling-form-page" method="post">
	<div>
		<label for="name">Name:</label>
		<input type="text" id="name" />
	</div>
	<div>
		<label for="mail">E-mail:</label>
		<input type="email" id="mail" />
	</div>
	<div>
		<label for="msg">Message:</label>
		<textarea id="msg"></textarea>
	</div>
</form>
```

> `<label>`
    
    - 위젯에 맞는 id를 참조하여, 사용자가 라벨을 눌렀을 때 해당하는 위젯을 활성화시킵니다.

    - Form 태그 앞에 출력되어 나옵니다.

> `<input>`

    - type 속성은 어떻게 입력을 받을 것인가를 결정합니다. (매우 중요한 속성!)

> `<textarea>`

    - 여러 줄의 긴 문장을 입력할 수 있는 입력 폼 입니다.

> `<input>` vs `<textarea>`

    - `<input>`의 경우 `<input value='default message'>` 처럼 value라는 속성을 이용하여 기본값을 저장합니다.

    - `<textarea>`는 `<textarea>default message</textarea>` 여는 태그와 닫는 태그 사이 내용에 값을 입력하면 기본값이 입력됩니다.

---

### `<button>`

```html
<div class="button">
	<button type="submit">Send your message</button>
</div>
```

> `submit 속성`
  
    - 폼 데이터를 `<form>` 요소의 action 속성에 정의된 웹페이지로 전송합니다.

> `reset 속성`
    
    - 모든 폼 위젯을 기본 값으로 바꿉니다.

> `button 속성`

    - 기본 행동이 없으며, 클릭했을 때 아무것도 하지 않습니다.

- ❗`<input>` 요소 역시 `type='button'`을 지정하여 버튼을 만들 수 있어요.

- `<button>` vs `<input type='button'>`
    - `<input>` 요소는 일반 텍스트만 보냅니다.
    - `<button>` 요소는 전체 HTML 콘텐츠를 보냅니다.

---

## 유효성 검사

### form의 유효성 검사란?

> 서버로 데이터를 제출하기 전, 포함되어야 할 정보들이 올바른 형식이고, 입력 조건에 맞게 잘 입력되었는지 확인하는 것을 말합니다.

- 예시
    - 👉 회원가입 시 아이디, 비밀번호, 이메일 주소 등을 입력하도록 하는 것
    - 👉 비밀번호 입력 시 문자, 숫자, 기호 조합 8자리 이상 지정하도록 하는 것

- form의 유효성 검사 방법은 HTML5의 유효성 검사 기능(built-in form validation)을 사용하는 것과 JavaScript를 이용한 유효성 검사 방법이 있습니다.

---

### HTML5의 유효성 검사 기능(built-in form validation)

> `<input>` 태그의 속성으로 다음과 같은 유효성 검사 기능을 지정할 수 있습니다.

- `required` : 필수로 입력해야합니다.
- `minlength` / `maxlength` : 최소 또는 최대 글자수를 지정합니다.
- `min` / `max` : 숫자의 최소 값 또는 최대 값을 설정합니다.
- `type` : 입력받을 데이터의 타입을 지정합니다. (email, password, number ... )
- `pattern` : 입력받을 데이터가 준수해야 할 정규 표현식을 설정합니다.

```html
<form>
	<label for="choose">Would you prefer a banana or cherry? (required)</label>
	<input id="choose" name="i_like" required> <!-- 필수록 입력해야 합니다. --> 
	<button>Submit</button>
</form>
```

---

```css
input:invalid {
  border: 2px dashed red;
}

input:invalid:required {
  background-image: linear-gradient(to right, pink, lightgreen);
}

input:valid {
  border: 2px solid black;
}
```

- CSS 스타일링 옵션에서도 `:valid`와 `:invalid` 를 이용해 유효성 검사를 통과하였을 때 혹은 통과하지 못하였을 때의 스타일링을 따로 지정하기도 합니다.
- [Constraint validation | MDN](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Constraint_validation#validation-related_attributes)

---

### JavaScript의 유효성 검사 기능

- 대부분의 브라우저는 **제약 조건 검증 API(Constraint Validation API)**를 지원합니다.
- [Constraint validation API | MDN](https://developer.mozilla.org/en-US/docs/Web/API/Constraint_validation)

> 예시
> 
> - `HTMLButtonElement` (represents a `<button>` element)
> - `HTMLFieldSetElement` (represents a `<fieldset>` element)
> - `HTMLInputElement` (represents an `<input>` element)
> - `HTMLOutputElement` (represents an `<output>` element)
> - `HTMLSelectElement` (represents a `<select>` element)
> - `HTMLTextAreaElement` (represents a `<textarea>` element)