# DummyAPI
Ручные тесты для объекта Post (Get List и Create Post), майндкарта. Автотесты для объекта Post

## Оглавление

1. [Описание](#описание-проекта)
2. Manual
   
   [Get list](#getpost-get-list)
 
   [Create post](#postcreate-create-post)

3. [Майндкарта](#майндкарта)
4. Automatic

   [Get list](getpost-get-list-1)
   
   [Create post](#postcreate-create-post-1)
   
5. [Коллекции](#коллекции-postman)    
## Описание проекта

https://dummyapi.io 

Сайт представляет собой сервис для тестирования API. Для выполнения запросов необходим app-id, который можно получить
после регистрации на сайте. В качестве тестирования был взят объект **Post**.

____

### GET/post (get list)
Возвращает список постов, отсортированных по дате создания.

- доступен query params для вывода определенной страницы.
- доступен query params для отображения числа постов.

**Response body**

```Javascript

{
            "id": "636a79ffce2f696653a14279",
            "image": "https://img.dummyapi.io/photo-1564694202779-bc908c327862.jpg",
            "likes": 0,
            "tags": [
                "animal",
                "dog",
                "golden retriever"
            ],
            "text": "adului",
            "publishDate": "2022-11-08T15:47:11.678Z",
            "updatedDate": "2022-11-08T15:47:11.678Z",
            "owner": {
                "id": "60d0fe4f5311236168a109ca",
                "title": "ms",
                "firstName": "Sara",
                "lastName": "Andersen",
                "picture": "https://randomuser.me/api/portraits/women/58.jpg"
            }
                  
  ```
  
  ___
  
 ### POST/create (create post) 
 
 Создает новый пост, возвращает данные о посте.
 
**Request body**

```Javascript

{
"image": "https://img.dummyapi.io/photo-1564694202779-bc908c327862.jpg",
"likes": 0,
"tags": [
"animal",
"dog",
"golden retriever"
],
"text": "Puopf",
"owner": "60d0fe4f5311236168a109ca"
}

```

___

**Response body**

```Javascript

{
    "id": "636c9607bbf5da30d217b99b",
    "image": "https://img.dummyapi.io/photo-1564694202779-bc908c327862.jpg",
    "likes": 0,
    "link": "",
    "tags": [
        "animal",
        "dog",
        "golden retriever"
    ],
    "text": "Puopf",
    "publishDate": "2022-11-10T06:11:19.936Z",
    "updatedDate": "2022-11-10T06:11:19.936Z",
    "owner": {
        "id": "60d0fe4f5311236168a109ca",
        "title": "ms",
        "firstName": "Sara",
        "lastName": "Andersen",
        "picture": "https://randomuser.me/api/portraits/women/58.jpg",
        "gender": "female",
        "dateOfBirth": "1996-04-30T19:26:49.610Z",
        "phone": "92694011",
        "location": {
            "street": "9614, SÃ¸ndermarksvej",
            "city": "Kongsvinger",
            "state": "Nordjylland",
            "country": "Denmark",
            "timezone": "-9:00"
        }
    }
}

```

___

## Майндкарта

Данная МК представляет собой набор тестов для тестирования объектов **POST**. Подробная проверка
расписана для **get list** и **create Post**. 

![Opera Снимок_2022-11-10_091712_www mindmeister com](https://user-images.githubusercontent.com/117887632/201015690-9a56b394-e64f-4809-a99b-b60e7c026b75.png)


Майндкарту можно [скачать] (https://github.com/Pol8289/DummyAPI/commit/d5d7849d1d8711fa1216b8b97fbfc69b6c290952)

## Автотесты 

Применялись к объекту **POST**. Проверка статус-кода

### GET/post (get list)

**Request body**

```Javascript

pm.test("Status code is 200", function () {
    pm.response.to.have.status(200);
});

```
**Response body**

PASS
Status code is 200

 ### POST/create (create post) 
 
 **Request body**

```Javascript

pm.test("Status code is 200", function () {
var jsonData = pm.response.json();
 console.log (jsonData);
pm.test("chek likes", function () {
    pm.expect(jsonData.likes).to.eql(0);
});
pm.test("chek image", function () {
    pm.expect(jsonData.image).to.eql("https://img.dummyapi.io/photo-1564694202779-bc908c327862.jpg");
pm.test("chek tags", function () {
    pm.expect(jsonData.tags).to.eql(["animal",
        "dog",
        "golden retriever"]);
        pm.test("chtk text", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.text).to.eql("adult Labrador");
});
});
});
    pm.response.to.have.status(200);
});
pm.test("owner", function () {
    var jsonData = pm.response.json();
    pm.expect(jsonData.owner.id).to.eql("60d0fe4f5311236168a109ca");

    pm.collectionVariables.set("id",jsonData.id);
});

```
**Response body**

PASS
chek likes
PASS
chtk text
PASS
chek tags
PASS
chek image
PASS
Status code is 200
PASS
owner

## Коллекции POSTMAN

Ручные тесты для объекта Post (Get List и Create Post) (https://github.com/Pol8289/DummyAPI/blob/main/DummyAPI%20(get%20list-create%20post).postman_collection.json)

Автотесты для объекта Post (https://github.com/Pol8289/DummyAPI/blob/main/DummyAPI%20(automatic).postman_collection.json)

Окружение (https://github.com/Pol8289/DummyAPI/blob/main/environment.postman_environment.json)














 
 
 
 
 
       
