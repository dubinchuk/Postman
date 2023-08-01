
### Postman homework #2

#### GET request endpoint /first 

1. Отправить запрос.

http://162.55.220.72:5005/first

2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Проверить, что в body приходит правильный string.
```
pm.test("Body is correct", function () {
    pm.response.to.have.body("This is the first responce from server!ss");
});
```
#### POST request endpoint /user_info_3

1. Отправить запрос.

http://162.55.220.72:5005/user_info_3

2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
const jsonData = pm.response.json();
```
4. Проверить, что name в ответе равно name s request (name вбить руками.)
```
pm.test("responce 'name' = request 'name'", function () {
    pm.expect(jsonData.name).to.eql("Evgeny");
});
```
5. Проверить, что age в ответе равно age s request (age вбить руками.)
```
pm.test("responce 'age' = request 'age'", function () {
    pm.expect(jsonData.age).to.eql("35");
});
```
6. Проверить, что salary в ответе равно salary s request (salary вбить руками.)
```
pm.test("responce 'salary' = request 'salary'", function () {
    pm.expect(jsonData.salary).to.eql(1000);
});
```
7. Спарсить request.
```
const reqData = request.data
```
8. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("responce 'name' = request 'name'", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
9. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("responce 'age' = request 'age'", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```
10. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("responce 'salary' = request 'salary'", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
});
```
11. Вывести в консоль параметр family из response.
```
console.log(jsonData.family)
```
12. Проверить что u_salary_1_5_year в ответе равно salary*4 (salary забрать из request)
```
pm.test("responce 'u_salary_1_5_year' = salary*4", function () {
    pm.expect(jsonData.family.u_salary_1_5_year).to.eql(reqData.salary*4);
});
```

#### GET request endpoint /object_info_3

1. Отправить запрос.

http://162.55.220.72:5005/object_info_3

2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
const jsonData = pm.response.json();
```
4. Спарсить request.
```
const reqData = pm.request.url.query.toObject();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("responce 'name' = request 'name'", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
6. Проверить, что age в ответе равно age s request (age забрать из request.)
```
pm.test("responce 'age' = request 'age'", function () {
    pm.expect(jsonData.age).to.eql(reqData.age);
});
```
7. Проверить, что salary в ответе равно salary s request (salary забрать из request.)
```
pm.test("responce 'salary' = request 'salary'", function () {
    pm.expect(jsonData.salary).to.eql(+reqData.salary);
});

```
8. Вывести в консоль параметр family из response.
```
console.log(jsonData.family);
```
9. Проверить, что у параметра dog есть параметры name.
```
pm.test("'dog' has 'name' property", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property("name");
});
```
10. Проверить, что у параметра dog есть параметры age.
```
pm.test("'dog' has 'age' property", function () {
    pm.expect(jsonData.family.pets.dog).to.have.property("age");
});
```
11. Проверить, что параметр name имеет значение Luky.
```
pm.test("'name' = 'Luky'", function () {
    pm.expect(jsonData.family.pets.dog.name).to.eql("Luky");
});
```
12. Проверить, что параметр age имеет значение 4.
```
pm.test("'age' = '4'", function () {
    pm.expect(jsonData.family.pets.dog.age).to.eql(4);
});
```

#### GET request endpoint /object_info_4


1. Отправить запрос.

http://162.55.220.72:5005/object_info_4

2. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
3. Спарсить response body в json.
```
const jsonData = pm.response.json();
```
4. Спарсить request.
```
const reqData = pm.request.url.query.toObject();
```
5. Проверить, что name в ответе равно name s request (name забрать из request.)
```
pm.test("responce 'name' = request 'name'", function () {
    pm.expect(jsonData.name).to.eql(reqData.name);
});
```
6. Проверить, что age в ответе равно age из request (age забрать из request.)
```
pm.test("responce 'age' = request 'age'", function () {
    pm.expect(jsonData.age).to.eql(+reqData.age);
});
```
7. Вывести в консоль параметр salary из request.
```
console.log(reqData.salary);
```
8. Вывести в консоль параметр salary из response.
```
let salary = jsonData.salary;
console.log(salary);
```
9. Вывести в консоль 0-й элемент параметра salary из response.
```
let salary0 = jsonData.salary[0];
console.log(salary0);
```
10. Вывести в консоль 1-й элемент параметра salary параметр salary из response.
```
let salary1 = jsonData.salary[1];
console.log(salary1);
```
11. Вывести в консоль 2-й элемент параметра salary параметр salary из response.
```
let salary2 = jsonData.salary[2];
console.log(salary2);
```
12. Проверить, что 0-й элемент параметра salary равен salary из request (salary забрать из request.)
```
pm.test("responce 'salary[0]' = request 'salary'", function () {
    pm.expect(salary0).to.eql(+reqData.salary);
});
```
13. Проверить, что 1-й элемент параметра salary равен salary*2 из request (salary забрать из request.)
```
pm.test("responce 'salary[1]' = request 'salary*2'", function () {
    pm.expect(+salary1).to.eql(reqData.salary*2);
});

```
14. Проверить, что 2-й элемент параметра salary равен salary*3 из request (salary забрать из request.)
```
pm.test("responce 'salary[2]' = request 'salary*3'", function () {
    pm.expect(+salary2).to.eql(reqData.salary*3);
});
```
15. Создать в окружении переменную name
```
pm.environment.set("name");
```
16. Создать в окружении переменную age
```
pm.environment.set("age");
```
17. Создать в окружении переменную salary
```
pm.environment.set("salary");
```
18. Передать в окружение переменную name
```
pm.environment.set("name", jsonData.name);
```
19. Передать в окружение переменную age
```
pm.environment.set("age", jsonData.age);
```
20. Передать в окружение переменную salary
```
pm.environment.set("salary", salary0);
```
21. Написать цикл который выведет в консоль по порядку элементы списка из параметра salary.
```
for (i = 0; i < salary.length; i++){
    console.log ("salary = " + salary[i])
}
```

#### POST request endpoint /user_info_2


1. Вставить параметр salary из окружения в request

Вводим в Body → form-data → salary значение `{{salary}}`

2. Вставить параметр age из окружения в age

Вводим в Body → form-data → age значение `{{age}}`

3. Вставить параметр name из окружения в name

Вводим в Body → form-data → name значение `{{name}}`

4. Отправить запрос.

http://162.55.220.72:5005/user_info_2

5. Статус код 200
```
pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});
```
6. Спарсить response body в json.
```
const jsonData = pm.response.json();
```
7. Спарсить request.
```
const reqData = request.data
```
8. Проверить, что json response имеет параметр start_qa_salary
```
pm.test("response has 'start_qa_salary' property", function () {
    pm.expect(jsonData).to.have.property("start_qa_salary");
});
```
9. Проверить, что json response имеет параметр qa_salary_after_6_months
```
pm.test("response has 'qa_salary_after_6_months' property", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_6_months");
});
```
10. Проверить, что json response имеет параметр qa_salary_after_12_months
```
pm.test("response has 'qa_salary_after_12_months' property", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_12_months");
});

```
11. Проверить, что json response имеет параметр qa_salary_after_1.5_year
```
pm.test("response has 'qa_salary_after_1.5_year' property", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_1.5_year");
});
```
12. Проверить, что json response имеет параметр qa_salary_after_3.5_years
```
pm.test("response has 'qa_salary_after_3.5_years' property", function () {
    pm.expect(jsonData).to.have.property("qa_salary_after_3.5_years");
});

```
13. Проверить, что json response имеет параметр person
```
pm.test("response has 'person' property", function () {
    pm.expect(jsonData).to.have.property("person");
});
```
14. Проверить, что параметр start_qa_salary равен salary из request (salary забрать из request.)
```
let reqSalary = +reqData.salary;
pm.test("responce 'start_qa_salary' = request 'salary'", function () {
    pm.expect(jsonData.start_qa_salary).to.eql(reqSalary);
});
```
15. Проверить, что параметр qa_salary_after_6_months равен salary*2 из request (salary забрать из request.)
```
pm.test("responce 'qa_salary_after_6_months' = request 'salary'*2", function () {
    pm.expect(jsonData.qa_salary_after_6_months).to.eql(reqSalary*2);
});
```
16. Проверить, что параметр qa_salary_after_12_months равен salary*2.7 из request (salary забрать из request.)
```
pm.test("responce 'qa_salary_after_12_months' = request 'salary'*2.7", function () {
    pm.expect(jsonData.qa_salary_after_12_months).to.eql(reqSalary*2.7);
});
```
17. Проверить, что параметр qa_salary_after_1.5_year равен salary*3.3 из request (salary забрать из request.)
```
pm.test("responce 'qa_salary_after_1.5_year' = request 'salary*3.3", function () {
    pm.expect(jsonData["qa_salary_after_1.5_year"]).to.eql(reqSalary*3.3);
});
```
18. Проверить, что параметр qa_salary_after_3.5_years равен salary*3.8 из request (salary забрать из request.)
```
pm.test("responce 'qa_salary_after_3.5_years' = request 'salary'*3.8", function () {
    pm.expect(jsonData["qa_salary_after_3.5_years"]).to.eql(reqSalary*3.8);
});
```
19. Проверить, что в параметре person, 1-й элемент из u_name равен salary из request (salary забрать из request.)
```
pm.test("responce 'u_name[1]' = request 'salary", function () {
    pm.expect(jsonData.person.u_name[1]).to.eql(reqSalary);
});
```
20. Проверить, что что параметр u_age равен age из request (age забрать из request.)
```
pm.test("responce 'u_age' = request 'age'", function () {
    pm.expect(jsonData.person.u_age).to.eql(+reqData.age);
});
```
21. Проверить, что параметр u_salary_5_years равен salary*4.2 из request (salary забрать из request.)
```
pm.test("responce 'u_salary_5_years' = request 'salary'*4.2", function () {
    pm.expect(jsonData.person.u_salary_5_years).to.eql(reqSalary*4.2);
});
```
22. ***Написать цикл который выведет в консоль по порядку элементы списка из параметра person.
```
for (let personKey in jsonData.person){
    console.log(`${personKey}: ${jsonData.person[personKey]}`);
}
```
Альтернативное решение:
```
for (let personKey in jsonData.person){
   console.log(personKey + ': ' + jsonData.person[personKey]);
}
```