# goit-markup-hw-05

                                      FORM

<form>
	<!-- Елементи форми -->

<button type="submit">Submit feedback</button>

</form>

Кнопка не успадковує багато стилів оформлення тексту.

Основні — це сімейство шрифтів і колір тексту. Рекомендується встановити глобальний стиль тегу button. Інші властивості та їх значення варто брати з макета.

button {
font-family: inherit;
color: currentColor;
}

                                      INPUT

<form>
  <input type="text" name="username" />
  <button type="submit">Submit feedback</button>
</form>

За замовчуванням поле введення є рядковим елементом, який не успадковує сімейство шрифтів.Отже, до глобальних стилів можна додати правило для всіх полів вводу.

input {
font-family: inherit;
}

                                       LABEL

<form>
  <label>
    Username
    <input type="text" name="username" />
  </label>
  <button type="submit">Submit feedback</button>
</form>

Якщо елемент форми не вкладено в label, необхідно явно зв'язати їх через:
атрибут id елемента та
атрибут for мітки

<form>
  <label for="username">Username</label>
  <input type="text" name="username" id="username" />
  <button type="submit">Submit feedback</button>
</form>

                                      PLACEHOLDER (текст-підказку)

<form>
  <label>
    Username
    <input type="text" name="username" placeholder="Jacob Mercer" />
  </label>
  <button type="submit">Submit feedback</button>
</form>

                                      ::PLACEHOLDER

Для оформлення тексту підказки використовується псевдоелемент ::placeholder.

input::placeholder {
color: teal;
font-weight: 700;
}

Змінити стилі тексту підказки при наведенні миші або фокусі поля введення можна селекторами стану.

input:hover::placeholder,
input:focus::placeholder {
color:orange;
}

                                        :placeholder-shown

Псевдоклас :placeholder-shown застосовується залежно від видимості тексту-підказки та значення атрибута placeholder.
Він дозволяє налаштовувати властивості поля вводу під час відображення тексту-підказки. Слід пам’ятати, що як тільки користувач ввів хоча б один символ, підказка зникає.

input {
border: 1px solid orange;
}

input:placeholder-shown {
border-color: blue;
}

Введи текст у поле форми.
Колір рамки поля зміниться на помаранчевий, щойно зникне текст підказки.

                                       AUTOFOCUS
                                       Фокус не може бути в декількох елементів одночасно. Отже, атрибут задається полю, з якого користувач має почати заповнювати форму. Атрибут autofocus — логічний, тобто без значення, вказується тільки назва.

<form>
  <label>
    First name
    <input type="text" name="firstName" autofocus />
  </label>
  <label>
    Last name
    <input type="text" name="lastName" />
  </label>
  <button type="submit">Submit</button>
</form>

                                         :focus-within

Застосовується до елемента, щойно він сам або елементи всередині нього отримують фокус. Це дозволяє застосувати стилі на:

мітку
форму
окреме поле форми
при взаємодії користувача з полями форми.

form:focus-within {
border-color: blue;
}

---

                                         TEXTAREA

Це може бути поле для:
зворотнього зв'язку
коментаря
посту в соцмережах
уточнення деталей замовлення тощо.

<textarea name="" rows="" cols="" placeholder=""></textarea>

textarea має такі атрибути:
rows — встановлює кількість рядків (висоту)
cols — встановлює кількість колонок (ширину)
На практиці вказується лише rows, а ширина елемента контролюється через CSS.

За замовчуванням елемент textarea можна розтягувати по горизонталі і вертикалі. Для того щоб контролювати можливість зміни розміру користувачем, CSS має властивість resize.

resize: both | horizontal | vertical | none

                                           SELECT

Елемент select — це випадаюче меню (або, як його ще називають, комбобокс), що дозволяє вибрати одну з декількох опцій (варіантів відповідей).

<select name="size">
  <option value="xs">Extra Small</option>
  <option value="s">Small</option>
  <option value="m" selected>Medium</option>
  <option value="l">Large</option>
</select>

Елемент select — це випадаюче меню з атрибутом name.
У меню вкладено набір елементів option з атрибутом value.
Текст усередині елемента option відображається в браузері, а значення атрибута value буде використано при відправленні форми.
За замовчуванням вибрано перший елемент option зі списку. Це можна змінити, задавши необхідну опцію атрибут selected.

                                              optgroup

Якщо потрібно згрупувати опції випадаючого меню, використовується тег optgroup.
Текст заголовка групи задають в атрибуті label.

<select name="month">
  <optgroup label="Summer">
    <option value="s6">June</option>
    <option value="s7">July</option>
    <option value="s8">August</option>
  </optgroup>

  <optgroup label="Autumn">
    <option value="s9">September</option>
    <option value="s10">October</option>
    <option value="s11">November</option>
  </optgroup>
</select>
