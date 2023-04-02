use library

db.createCollection("books")

- запрос(ы) для *вставки* данных минимум о двух книгах в коллекцию **books**:

db.books.insertMany([
    {
        title: "string",
        description: "string",
        authors: "string"
    },
    {
        title: "string",
        description: "string",
        authors: "string"
    },
])

- запрос для *поиска* полей документов коллекции **books** по полю *title*:

db.books.find({title: {$exists: true}})

- запрос для *редактирования* полей: *description* и *authors* коллекции **books** по *_id* записи:

db.books.updateMany(
    {_id: ObjectId("6429cdbc96d8f27fc5790e0e")
    },
    {
        $set: {
            description :"test",
            authors :"test"
        }
    }
)
