# Lead Programmer's Guidelines

## Designing Systems

### Standardize Error-Handlings
Standardize error-handlings among cooperators.

good:
```
You (lead programmer) defines NotAuthorizedException and tells cooperators to throw them when User is not authorized.
Alice throws NotAuthorizedException if User is not authorized.
Bob throws NotAuthorizedException if User is not authorized.
```
bad:
```
You defines nothing.
Alice redirects User if he is not authorized.
Bob shows a cutstom error message to User if he is not authorized.
```

## 
