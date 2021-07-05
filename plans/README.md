# Quy Định Plan

```typescript
export interface Plan {
    showBrand: boolean
    enableMailServices: boolean
    enableAnalytics: boolean
    goals: all | string[]
    numberOfSmartbars: number
    numberOfPopups: number
    layout: all | string[]
}
```

## Goal Supported

**Là các target năng được hỗ trợ trong một plan.**

Có các Goal dưới đây:

1. email
2. email_wheel
3. email_coupon_follows
4. social_follows
5. target_image_url
6. target_url
6. announcement

## Templates Supported

**Các mẫu templates được hỗ trợ**
https://www.dropbox.com/s/c1be9sluhau6r5i/Screen%20Shot%202021-06-30%20at%2016.43.00.png?dl=0

## Các Plan Hỗ Trợ

### Original Free

Khi app mới lên, gói Free này sẽ mở nhiều tính năng hơn gói Free sau này.

```typescript
export interface OriginalFree {
    showBrand: true
    enableMailServices: true
    enableAnalytics: true
    goal: all
    numberOfSmartbars: 1
    numberOfPopups: 1
    layout: all
}
```

###  Free

```typescript
export interface Free {
    showBrand: true
    enableMailServices: false
    enableAnalytics: false
    goal: ["email", "email_coupon_follows", "social_follows"]
    numberOfSmartbars: 1
    numberOfPopups: 1
    layout: ["layout1"]
}
```

### Silver

```typescript
export interface Silver {
    showBrand: false
    enableMailServices: true
    enableAnalytics: true
    goals: ["email", "email_coupon_follows", "social_follows", "target_url"]
    numberOfSmartbars: 5
    numberOfPopups: 5
    layout: ["layout1", "layout2"]
}
```

### Gold

```typescript
export interface Gold {
    showBrand: false
    enableMailServices: true
    enableAnalytics: true
    goals: "all"
    numberOfSmartbars: 100
    numberOfPopups: 100
    layout: "all"
}
```
