# Task_GraphQL
Task_GraphQL
На основе документации в Confluence https://testbase.atlassian.net/wiki/spaces/GraphQL/pages/4427939842/Cards
1.Создать 3 новых users.
2.У новых users создать банковские карточки.
3.Добавить на банковские карточки деньги.

1.Для создания новых юзеров используем mutation AddUser.

mutation AddUser {
    addUser(name: "Инокентий", age: 30, phone: "123", vip: false) {
        id
        name
        age
        phone
        vip
    }
}


mutation AddUser {
    addUser(name: "Фарид", age: 45, phone: "3452", vip: false) {
        id
        name
        age
        phone
        vip
    }
}


mutation AddUser {
    addUser(name: "Цой", age: 60, phone: "7777", vip: false) {
        id
        name
        age
        phone
        vip
    }
}

2.Для создания карточек используем mutation AddCard.

Иннокентий_id:8;
Фарид_id:9,
Цой_id:7


mutation AddCard {
    addCard(bank: GREEN_BANK, number: "4321-4321-4321-4321", user_id: 8) {
        bank
        number
        balance
    }
}

mutation AddCard {
    addCard(bank: GREEN_BANK, number: "3421-3421-3421-3421", user_id: 9) {
        bank
        number
        balance
    }
}

mutation AddCard {
    addCard(bank: RED_BANK, number: "2413-2413-2413-2413", user_id: 7) {
        bank
        number
        balance
    }
}

3.Для добавления на банковские счета денег используем mutation AddMoney.

mutation AddMoney {
    addMoney(number: "4321-4321-4321-4321", balance: 1000.0) {
        bank
        number
        balance
    }
}


mutation AddMoney {
    addMoney(number: "3421-3421-3421-3421", balance: 3000.0) {
        bank
        number
        balance
    }
}

mutation AddMoney {
    addMoney(number: "2413-2413-2413-2413", balance: 7000.0) {
        bank
        number
        balance
    }
}


