# AVL Tree Rotations

## Introduction

## Rotations

## Determining the Rotations Needed

single rotation

- If N and C are heavy in the same direction (i.e., if the balance factor has the same sign at both N and C), then a single rotation is needed around N in the opposite direction as N’s heaviness. 

double rotation

- In a double rotation, we rotate twice. 

- If N is left-heavy and C is right-heavy (i.e., N has a negative balance factor and C has a positive balance factor) then we first rotate left around C then right around N. This is also known as an L-R case. 

-  If N is right-heavy and C is left-heavy (i.e., N has a positive balance factor and C has a negative balance factor) then we first rotate right around C then left around N. This is also known as an R-L case. 

![](single.png)

![](double.png)


