Bare minimum web app using Express. Supports basic user authentication using Passport. Uses Jade template engine. 

Usernames and passwords are stored in a local MongoDB database. For local prototyping only; **never use unencrypted passwords in production** (check out the *bcrypt-nodejs* package). 

## MongoDB Details

**Database:** UserDatabase  
**Collection:** userInfo

To insert new user: `db.userInfo.insert({username: 'admin', password: 'admin'})`

```
// connect to local database
mongoose.connect('mongodb://localhost/UserDatabase');
var Schema = mongoose.Schema;
var UserSchema = new Schema({
  username: String,
  password: String
}, {
  collection: 'userInfo'
});
var UserModel = mongoose.model('userInfo', UserSchema); 
```
