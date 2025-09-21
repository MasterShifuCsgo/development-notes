# Project Development Rules

#### 1. **Plan Before Coding**

- Define **entities, relationships, and API contracts** before any implementation.
    
- Write this down in a **markdown spec** (data structures, endpoints, flows).
    
- No frontend code until the backend structure is stable.
    

#### 2. **Start Small with Backend**

- Build the **minimum viable backend** first:
    
    - CRUD endpoints for the core entity only.
        
    - Predictable, clean responses.
        
    - Validation and error handling included **from the start**.
        

#### 3. **Frontend Decoupling**

- Frontend communicates only through **documented API endpoints**.
    
- No shared assumptions outside explicit contracts.
    
- Build a **dedicated API service layer** (e.g., a wrapper for `fetch`).
    

#### 4. **Commit Discipline**

- **One purpose per commit**: feature, bug fix, refactor, docs, or style — never mixed.
    
- If you can’t describe the commit in a short sentence, split it.
    
- `main/master` must always stay **stable and deployable**.
    
- Use **feature branches**, merge only after testing and reviewing.
    

#### 5. **Tests Early**

- Add tests as soon as a feature stabilizes.
    
- Minimum coverage:
    
    - API endpoint tests.
        
    - Critical frontend components.
        
- Tests catch breakage, not manual checking.
    

#### 6. **Lock Interfaces**

- Once a feature or API endpoint is live, **freeze its interface**.
    
- Breaking changes (`refactor!`) must be rare and planned.
    

#### 7. **Avoid Over-Engineering**

- No global state managers or reusable components **until proven necessary**.
    
- **YAGNI**: _You Aren’t Gonna Need It._
    

#### 8. **Track Decisions**

- Record every significant technical decision in a short **ADR (Architecture Decision Record)**.
    
- Prevents forgetting why a choice was made.
    

#### 9. **Clean as You Go**

- Remove unused files, functions, and components **immediately**.
    
- Never leave TODOs or debug logs for "later cleanup."
    

#### 10. **Define “Done” State**

A feature is done only when:

- All tests pass.
    
- Code linted and styled consistently.
    
- Documentation updated if relevant.
    
- No TODO comments or console logs remain.
    

#### 11. **Helper Functions and Abstraction**

- Build helper functions to remove redundant code — **even for strings**.
    
- Centralize repetitive actions:
    
    - Example: no duplicate `fetch` calls; use one API wrapper.
        

#### 12. **Consistent Styling**

- Define **hard-coded spacing units** and **color palette** in code.
    
- Create a style guide for components (Tailwind utilities, theme constants).
    

#### 13. **User Feedback for Errors**

- Every error must notify the user.
    
- Use a standardized error handling tool like [React Hot Toast](https://react-hot-toast.com/).
    

#### 14. **State Management Simplicity**

- Combine related state values into a **single state object** instead of scattering with multiple `useState` hooks.
    

#### 15. **Clear Component Contracts**

- Each component must have a clearly defined purpose:
    
    - What it does.
        
    - What props it takes.
        
    - What it returns.
        
- Once a component is finalized, **do not modify it casually**.
    

#### 16. **Folder and File Organization**

- Group files **by feature/domain**, not by random type.
    
- Example:
    
    `/features   /foods     FoodList.jsx     FoodDetails.jsx     foodApi.js`
    
- Avoid a chaotic flat structure.
    

#### 17. **Avoid Scattered Checks**

- A function must own its responsibility.
    
- Do not add random “just in case” checks outside the function.
    
- Example:
    
    `// Bad const numberf = NumberFormatter(name, number || 0);  // Good const numberf = NumberFormatter(name, number); // Let NumberFormatter handle the defaulting`
    

#### 18. **Stop When Design Feels Shaky**

- If changes keep looping or architecture feels unstable:
    
    - **Pause coding.**
        
    - Diagram the system.
        
    - Decide on a fix.
        
    - Then resume work.
        

---

### Key Mindset Rules

- **Problem-Solving First:** better problem-solving leads to cleaner code and simpler solutions.
    
- **Read Proven Resources:** study books like _Clean Code_ and _Clean Architecture_ to improve code quality mindset.
    
- **Systems Thinking:** avoid patchwork fixes; think in terms of long-term maintainable systems.
    
- **Minimize Technical Debt:** prioritize clarity and stability over speed.
    

---

### Workflow Summary

1. Plan architecture and write specs.
    
2. Build minimal backend with clean API contracts.
    
3. Lock interfaces before frontend work begins.
    
4. Use disciplined, atomic commits and feature branches.
    
5. Add tests early and keep them updated.
    
6. Build helper functions to centralize redundant code.
    
7. Keep frontend styling consistent and standardized.
    
8. Freeze designs; pause when architecture feels shaky.
    
9. Constantly clean up and remove unnecessary files.
    
10. Release only when a feature fully meets the “done” criteria.
