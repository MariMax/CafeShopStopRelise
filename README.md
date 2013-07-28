Важные замечания, показывать кафе на карте можно если у него есть хоть один подтвержденный пользователь, иначе нельзя.

Пользователь считается подтвержденным, если он подтвердил свой Email
Кафе считается подтвержденным, если оно подтвердило свой сотовый телефон

Пользователи умеют: </br>
1) Создаваться /users/newUser</br>
2) Подтверждать email, после создания ссылка на подтверждение отправляется на email или как минимум записывается в лог</br>
3) Логин/Логоут /users/login или /users/logout</br>
пока не актуально 4) Можно связать пользователя с кафе /users/assignwithcafe требуется указать UserId и CafeId</br>
тоже не актуально 5) Можно подтвердить пользователя в кафе, т.е. дать ему возможность работать /users/approveuserincafe. Условия такие вызывает этот метод залогиненый сотрудник кафе, иначе ничего не выйдет</br>
6) Можно получить текущее кафе пользователя /users/getcafe/userId работает для любого сотрудника как подтвержденного так и не очень, и даже если у него нет кафе</br>
7) Можно получить пользователя /users/getuser/userId вернет либо пользователя, либо скажет что его нет</br>
8) /users/update: Переименовать пользователя;
9) 				  Можно поменять пользователю email;
10) 			  Можно сменить пароль пользователя;
11) Восстановление пароля /users/forgot-password план такой, переходим по ссылке, вводим email далее идем на почту или в логи, переходим по ссылке подтверждения, и на почту или в логи падает новый пароль</br>
</br>
Вроде все, и даже проверено, если чего-то не хватает по пользователям, можно дописывать, буду доделывать</br>
</br>
При смене кафешки, если из текущей ушел последний пользователь её надо будет удалять.... забил на это, пока лень, мусор так мусор потом разбермся, главное не удалить эту строку</br>
</br>
Кафе</br>
1) Залогиненый пользователь может создать себе собственное кафе(сразу к нему привязывается и подтверждается в нем, также в кафе создается меню) в котором потом сможет работать /cafes/newCafe</br>
2) Можно получить всех подтвержденных в кафе пользователей /cafes/getApprovedUsers/cafeId</br>
3) Можно получить список вообще всех пользователей привязанных к кафе /cafes/getAllUsers/cafeId</br>
4) Можно поменять любые данные о кафе, кроме сотового телефона /cafes/updateValues/cafeId доступно залогиненому сотруднику кафе</br>
5) Можно поменять сотовый телефон /cafes/updateCellPhone/cafeId доступно залогиненому сотруднику кафе</br>
6) Можно подтверлить сотовый телефон /cafes/approve-CellPhone обязательные параметры cafeId, token код верификации и номер телефона.</br>
7) Надо доделсть подтверждение сотового, чтобы была форма

По кафе все проверено, и все работает

TODO: в форму администрирования кафе добавить возможность подтвердить сотовый телефон, т.е. после его изменения 
1) проверять на валидность
2) сравнивать со старым
3) если изменился добавить кнопку верификации
4) отправить sms, вывести окно верификации
5) проверить код, сравнить с БД и записать
TODO: в форму администрирования кафе добавить возможность указать кафе на карте
1) после нажатия на кнопку должена пропасть форма, оставляем только чистую карту
2) после двойного клика на карте мы должны сохранить новые координаты этого кафе в БД
3) Добавить кнопку просмотра своего кафе на карте, т.е. при нажатии на данную кнопку пользователь видитгде распологается его кафе 