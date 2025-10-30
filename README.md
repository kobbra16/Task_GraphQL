# Task_GraphQL
Task_GraphQL
На основе документации в Confluence 
>https://testbase.atlassian.net/wiki/spaces/GraphQL/pages/4427939842/Cards
1.Создать 3 новых users.
2.У новых users создать банковские карточки.
3.Добавить на банковские карточки деньги.
4.Провести деньги с карточки на карточку.

1.Для создания новых юзеров используем mutation addUser.
```
mutation addUser {
    addUser(name: "Инокентий", age: 30, phone: "123", vip: false) {
        id
        name
        age
        phone
        vip
    }
}


mutation addUser {
    addUser(name: "Фарид", age: 45, phone: "3452", vip: false) {
        id
        name
        age
        phone
        vip
    }
}


mutation addUser {
    addUser(name: "Цой", age: 60, phone: "7777", vip: false) {
        id
        name
        age
        phone
        vip
    }
}
```
2.Для создания карточек используем mutation addCard.
```
mutation addCard {
    addCard(bank: GREEN_BANK, number: "4321-4321-4321-4321", user_id:{{id}}) {
        bank
        number
        balance
    }
}

mutation addCard {
    addCard(bank: GREEN_BANK, number: "3421-3421-3421-3421", user_id:{{id}}) {
        bank
        number
        balance
    }
}

mutation addCard {
    addCard(bank: RED_BANK, number: "2413-2413-2413-2413", user_id:{{id}}) {
        bank
        number
        balance
    }
}
```
3.Для добавления на банковские счета денег используем mutation addMoney.
```
mutation addMoney {
    addMoney(number: "4321-4321-4321-4321", balance: 1000.0) {
        bank
        number
        balance
    }
}


mutation addMoney {
    addMoney(number: "3421-3421-3421-3421", balance: 3000.0) {
        bank
        number
        balance
    }
}

mutation addMoney {
    addMoney(number: "2413-2413-2413-2413", balance: 7000.0) {
        bank
        number
        balance
    }
}
```
4.Для перевода между карточками используем метод MoneyTransfer.
```
mutation MoneyTransfer {
    moneyTransfer(number_from: "3421-3421-3421-3421", number_to:"2413-2413-2413-2413", balance: 1000) {
        bank
        number
        balance
    }
}
```

