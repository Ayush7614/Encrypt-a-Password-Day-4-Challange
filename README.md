# Using passlib
# To install passlib, all we need to do is:
`pip install passlib`

The CryptContext
Passlib works by defining a context. In it, we specify what algorithm we'll use for hashing, as well as any configuration parameters.

We can skip using a CryptContext, and instead interacting with the hashing algorithm directly. Passlib provides a way to do this. However, using a CryptContext allows us to more explicitly define configuration parameters, and makes things more readable. Also, it allows us to support multiple algorithms at once should that be a requirement for our system.

Creating the context with PBKDF2 is done like as below. Place the following code in a new file (e.g. security.py):

Encrypting and verifying passwords
Now that we have our CryptContext, we can use it to encrypt and verify passwords. Let's add a couple functions inside the same file where we created the context:

def encrypt_password(password):
    return pwd_context.encrypt(password)


def check_encrypted_password(password, hashed):
    return pwd_context.verify(password, hashed)

