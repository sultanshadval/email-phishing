import email
from email.policy import default

def analyze_email(email_content):
    msg = email.message_from_string(email_content, policy=default)
    for part in msg.walk():
        if part.get_content_type() == 'text/plain':
            body = part.get_payload(decode=True).decode('utf-8')
            if 'http://' in body or 'https://' in body:
                print("Suspicious link found in email body")
    print(f"From: {msg['From']}")
    print(f"Subject: {msg['Subject']}")

email_content = """
From: phishing@example.com
Subject: Update Your Account Information
Body: Please visit http://phishing-link.com to update your account.
"""
analyze_email(email_content)
