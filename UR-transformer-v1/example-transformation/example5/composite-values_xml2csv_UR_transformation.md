# Example #5 - Composite new values

> Ideas:
>
> First shift quest-id, part-num, latitude and longitude to new array of numbered row objects, then combine quest-id and part-num into quest-part-id and then remove quest-id and part-num properties.
>
> This we will probably not be able to do, but we can shift the values into four columns 'quest-id', 'part-num', 'latitude', 'longitude'
>
> We have another problem tho, how to put the quest-id into all the appropriate row objects, when these object do not yet exist when parsing guest-id and we dont know how many of them there will be...
