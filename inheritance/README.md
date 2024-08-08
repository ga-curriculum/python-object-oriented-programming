<h1>
  <span class="headline">Python Object-Oriented Programming</span>
  <span class="subhead">Inheritance</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to explain the concept of inheritance in object-oriented programming, create subclasses that inherit properties and methods from a parent class, and utilize the `super()` function to extend and customize class behavior.

| Lesson      | Duration |
| ----------- | -------- |
| Inheritance | 10 min   |

## Moving From General to Specific Classes

Nearly every application will have the concept of a User. However, there are more specific types of users with different functionality and properties:

- Admin users have access to nearly everything behind the scenes.
- Moderators might have editing capabilities over user-created content.
- Team leaders have authority over a specific group of user accounts.

Depending on the application, a wide range of more specific Users could be necessary to restrict or enhance a given user's abilities.

## Creating Specific Sub-Classes with Inheritance

One of the most powerful concepts of Object-Oriented Programming is the ability for a class to **inherit** base functionality from a parent class, then **extend** in more specific ways.

- The User class would contain everything common to all users.
- The Admin class would have all the same functionality as a regular User, plus more specific properties and methods.

## Inheritance Example

```python
class User:
    all_users = []
    def __init__(self, username):
        self.username = username
        self.can_post = True
        all_users.append(self)
```

```python
class Admin(User):
    def __init__(self, username):
        super().__init__(username)

    def suspend_user(username):
        for user in User.all_users:
            if user.username == username:
                user.can_post = False
```

Note the `super` method. It accesses the parent class. Why do we want to call the parent's `__init__` function?

> The `super()` pattern can be super annoying when learning inheritance. We need to use it so that Admins are created with all the same steps as a regular User.

# Optional Practice

## Solo Exercise: Bands Part 2 20 min TKTK

Create subclasses that inherit from the Band class created earlier according to specifications described in the Jupyter Notebook.

## Solo Exercise: RPG Characters 45 min TKTK

Use inheritance to set up a combat simulation for a Role-Playing Game. The Character class will set up default properties for every character in the game, while the more specific classes will create more interesting, playable characters.
