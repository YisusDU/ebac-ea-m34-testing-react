# 🧭 HoundExpress -  Guide Tracking System

![React](https://img.shields.io/badge/React-61DAFB?style=flat&logo=react&logoColor=black)
![Redux Toolkit](https://img.shields.io/badge/Redux--Toolkit-764ABC?style=flat&logo=redux&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=flat&logo=typescript&logoColor=white)
![Styled Components](https://img.shields.io/badge/Styled--Components-DB7093?style=flat&logo=styled-components&logoColor=white)
![React Testing Library](https://img.shields.io/badge/React%20Testing%20Library-E33332?style=flat&logo=testing-library&logoColor=white)
![Jest](https://img.shields.io/badge/Jest-C21325?style=flat&logo=jest&logoColor=white)
![Create React App](https://img.shields.io/badge/Create--React--App-09D3AC?style=flat&logo=create-react-app&logoColor=white)
---
## Preview
<img src="https://github.com/YisusDU/ebac-ea-m38-SEO/blob/main/houndxpress2/src/assets/IMG/preview-hx.webp" alt="general-preview">

## 📂 Relevant Source Files

- `houndxpress2/src/App/__test__/App.test.tsx`
- `houndxpress2/src/components/__tests__/GuideRegister.test.tsx`
- `houndxpress2/src/state/__tests__/guidesSlice.test.ts`

---

## 🎯 Purpose and Scope

This document provides a **comprehensive introduction** to **HoundXpress2**, a **React-based logistics tracking application** designed for managing shipment guides (deliveries).  
It covers:

- System purpose  
- Main features  
- Technology stack  
- High-level architecture

➡️ For setup instructions, see **Getting Started**  
➡️ For architecture details, see **Architecture Overview**  
➡️ For Redux state logic, see **State Management**

---

## 🧬 System Overview

**HoundXpress2** is a **web-based logistics management system** that enables users to:

- Create, track, and update shipment guides  
- Use a centralized dashboard  
- Interact through a modern React interface

### 🧱 Core Business Domain

The system manages **Guide** entities representing shipments. Each Guide includes:

- Origin, destination, recipient info  
- A list of `GuideStage` entries recording status history over time

> **Sources:**  
> `GuideRegister.test.tsx` (lines 157–171)  
> `guidesSlice.test.ts` (lines 17–33)

---

## ⚙️ Core Features

| Feature             | Description                          | Primary Component          |
|---------------------|--------------------------------------|-----------------------------|
| **Guide Registration** | Create new shipment guides with validation | `GuideRegister`          |
| **Guide Listing**   | Display and filter existing guides   | `GuideList`                |
| **Status Updates**  | Update guide delivery status         | `ModalUpdate`, `UpdateForm`|
| **History Tracking**| View complete guide timeline         | `ModalHistory`, `HistoryPath` |
| **Dashboard Analytics** | Display guide statistics             | `GeneralState`             |

Business rules enforced:

- Unique guide numbers  
- Required field validation

> **Sources:**  
> `GuideRegister.test.tsx` (lines 133–154)  
> `App.test.tsx` (lines 54–70)

---

## 🧰 Technology Stack

| Technology            | Description                         |
|------------------------|-------------------------------------|
| **React 18 + TypeScript** | Frontend framework                |
| **Redux Toolkit**     | State management (@reduxjs/toolkit) |
| **Styled Components** | CSS-in-JS with ThemeProvider        |
| **React Testing Library + Jest** | Component/unit testing   |
| **Create React App**  | Build configuration                 |

The app uses:

- Functional components  
- Custom hooks for business logic  
- Centralized state via Redux

> **Sources:**  
> `GuideRegister.test.tsx` (lines 4–8)  
> `App.test.tsx` (lines 4–9)

---

## 🧱 Application Architecture

### 🧩 Component Hierarchy

> *(Insert diagram here if available)*  
The diagram illustrates how:

- The `App` component serves as root  
- Layout and logic are orchestrated  
- Components interact with `GuidesSlice` via Redux

> **Sources:**  
> `App.test.tsx` (lines 36–100)  
> `GuideRegister.test.tsx` (lines 25–33)

---

## 🔁 State Management Flow

React components dispatch **Redux actions** to modify the central `GuidesState`.  
Two core structures:

- `guides`: all shipment guides  
- `modalData`: current modal type & target guide

> **Sources:**  
> `guidesSlice.test.ts` (lines 1–7 and 104–124)

---

## 🧾 Data Models

### 📦 Guide Entity

```ts
{
  guide__number: string,
  guide__origin: string,
  guide__destination: string,
  guide__recipient: string,
  guide__stage: GuideStage[]
}
```
🕒 GuideStage Entity
```
{
  guide__date: string,
  guide__status: string,
  guide__hour: string
}
Each Guide includes a chronological array of GuideStage entries, tracking the complete shipment lifecycle.
```
Sources:
```
GuideRegister.test.tsx (lines 235–248)
guidesSlice.test.ts (lines 55–62)
```
## 🧪 Testing Strategy
The application includes comprehensive testing using:

## ✅ Component Testing
- Rendering checks

- Simulated user interactions

- UI-state integration

## 🔁 State Management Testing
- Redux actions

- Reducers

- State transitions

### 🌐 Integration Testing
- End-to-end flows (e.g., create + update guide)

- Test files follow this convention:

- ComponentName.test.tsx → React component tests

- sliceName.test.ts → Redux & utility tests


## Sources:
```
GuideRegister.test.tsx (lines 11–250)
guidesSlice.test.ts (lines 10–125)
App.test.tsx (lines 35–101)
```

>[!Note]
>You can check the full documentation <a href="https://deepwiki.com/YisusDU/ebac-ea-m34-testing-react">-here-</a>
