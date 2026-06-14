# How to Enable OTP Email Sending

## The one thing you need to do

Open this file:  **Voting/Voting/settings.py**

Find this line near the bottom:
```
EMAIL_HOST_PASSWORD = ''   # <-- paste your 16-char App Password here
```
Paste your Gmail App Password there. That's it.

---

## How to get your Gmail App Password (5 minutes)

1. Go to: https://myaccount.google.com/security
2. Click **"2-Step Verification"** and turn it ON (required)
3. Go to: https://myaccount.google.com/apppasswords
4. Under **"Select app"** choose **Mail**
5. Under **"Select device"** choose **Other** → type `VotingApp`
6. Click **Generate**
7. Google shows a 16-character password like: `abcd efgh ijkl mnop`
8. Copy it and paste into `settings.py` **without spaces**: `abcdefghijklmnop`

Example of what settings.py should look like after:
```python
EMAIL_HOST_USER     = 'saniabraganza9@gmail.com'
EMAIL_HOST_PASSWORD = 'abcdefghijklmnop'   # your actual app password
```

9. Save the file and **restart the Django server** (Ctrl+C then `python manage.py runserver`)

---

## What happens without the App Password

The app still works — OTP is shown directly on the screen in a yellow box.
The user just copies that number into the OTP field and clicks Verify.
Once you set the App Password, OTPs will go to the voter's actual email inbox.
