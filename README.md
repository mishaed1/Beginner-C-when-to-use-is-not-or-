# Beginner Csharp when to use - is not or !=

## **`!=` vs `is not` — which should you use?**

Both are valid in C#, but they are **not interchangeable**. They serve different purposes.

---

## **1. `!=` — the classic inequality operator**
Use this for **value comparisons**:

- numbers  
- strings  
- enums  
- structs  
- most everyday comparisons  

```csharp
if (x != 5) { ... }
if (name != "Seeu") { ... }
```

It calls the type’s `!=` operator overload if one exists.

---

## **2. `is not` — pattern matching**
Use this when you want to check **types**, **null**, or **patterns**:

```csharp
if (obj is not null) { ... }
if (shape is not Circle c) { ... }
if (value is not int i) { ... }
```

`is not` is part of the pattern‑matching system introduced in modern C#.

---

## When to choose which

### Use **`!=`** when:
- You’re comparing values  
- You expect operator overloads  
- You want the “normal” inequality semantics  

### Use **`is not`** when:
- You’re checking **null** in modern C#  
- You’re checking **types**  
- You’re using **pattern matching**  
- You want to avoid overloaded `==`/`!=` behavior  

---

## The subtle but important difference

`obj != null` can be overloaded (e.g., Unity’s weird null behavior).  
`obj is not null` **cannot** be overloaded — it’s guaranteed to be a real null check.

That’s why many modern C# devs prefer:

```csharp
if (obj is not null)
```

---

## Bottom line

- For **value inequality** → use `!=`  
- For **type/null/pattern checks** → use `is not`  
- For **safe null checks** → prefer `is not null`  

