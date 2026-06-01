# n8n-github-workflow
# GitHub Top Repositories Workflow (n8n)

## 📌 Project Overview
This workflow fetches the top 5 most popular JavaScript GitHub repositories and enriches them with GitHub user details like followers count using API integration in n8n.

---

## 🔗 APIs Used

### 1. GitHub Search API
https://api.github.com/search/repositories

- Fetches repositories based on topic: JavaScript  
- Sorted by stars (highest first)  
- Returns repo name, stars, owner, URL  

### 2. GitHub Users API
https://api.github.com/users/{username}

- Fetches user profile details  
- Used to get follower count  

---

## 🔄 Workflow Steps

1. **Schedule Trigger**
   - Runs workflow automatically

2. **HTTP Request (Repo API)**
   - Fetches repositories from GitHub

3. **Code Node**
   - Extracts top 5 repositories
   - Keeps only required fields:
     - name
     - stars
     - url
     - owner

4. **HTTP Request (User API)**
   - Fetches followers for each repo owner

5. **Final Code Node**
   - Combines repo + user data into final output

---

## 📊 Final Output Example

- name: react  
- stars: 245000+  
- owner: facebook  
- url: https://github.com/facebook/react  
- followers: 100000+  

---

## ⚠️ Error Handling

- If API fails → workflow continues  
- Missing data → shows null or 0  
- Safe fallback used in Code nodes  
- No workflow crash on single API failure  

---

## 🎯 Purpose

This project demonstrates:
- API integration in n8n  
- Data transformation using Code node  
- Multi-API chaining  
- Workflow automation skills  

---

## 🚀 Result

A fully automated workflow that combines GitHub repository data with user analytics in a single structured output.
