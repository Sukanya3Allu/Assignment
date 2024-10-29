Question 1:

Code Example:

Python:

from django.db.models.signals import post_save
from django.dispatch import receiver

class MyModel(models.Model):
    # ...

@receiver(post_save, sender=MyModel)
def my_signal_handler(sender, instance, **kwargs):
    print("Signal received")
    # Perform some long-running task here

Question 2:

Code Example:

Python:

 from django.db.models.signals import post_save
from django.dispatch import receiver
from threading import current_thread

class MyModel(models.Model):
    # ...

@receiver(post_save, sender=MyModel)
def my_signal_handler(sender, instance, **kwargs):
    print("Signal thread ID:", current_thread().ident)

# Trigger the signal
my_object = MyModel.objects.create(...)

Question 3:

Code Example:

Python:

from django.db.models.signals import post_save
from django.dispatch import receiver

class MyModel(models.Model):
    # ...

@receiver(post_save, sender=MyModel)
def my_signal_handler(sender, instance, **kwargs):
    # Perform database operations here, which will be part of the same transaction
    RelatedModel.objects.create(my_model=instance)


Custom Classes in Python

class Rectangle:
    def __init__(self, length, width):
        self.length = length
        self.width = width

    def __iter__(self):
        yield ('length', self.length)
        yield ('width', self.width)

# Example usage:
rect = Rectangle(5, 10)
for item in rect:
    print(item)  # Output: ('length', 5), ('width', 10)


