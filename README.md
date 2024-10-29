Question 1:
By default, Django signals are executed synchronously. This means they are executed within the same thread as the signal sender.
Code Example:

from django.db.models.signals import post_save
from django.dispatch import receiver

class MyModel(models.Model):
    # ...

@receiver(post_save, sender=MyModel)
def my_signal_handler(sender, instance, **kwargs):
    print("Signal received")
    # Perform some long-running task here
