# 🎓 University Digital Twin - NGSI-v2 with FIWARE Orion

This project models a digital twin of a university using FIWARE's Orion Context Broker and the NGSI-v2 API standard. It defines and manages virtual representations (entities) of real-world university components such as buildings, classrooms, students, and professors.

---

## 🚀 What’s Inside?

- 🏛️ University entity
- 🏢 Buildings linked to the university
- 🧑‍🏫 Professors assigned to classrooms
- 🧑‍🎓 Students enrolled in the university
- 🧩 Relationships like `partOf`, `locatedIn`, `teachesIn`, and `enrolledIn`

---

## ⚙️ Requirements

- Docker
- Git
- FIWARE Orion Context Broker (via Docker Compose)

---

## 📦 Setup

1. **Clone the repo**

```bash
git clone https://github.com/your-username/university-digital-twin.git
cd university-digital-twin
```
2. **Start Orion and MongoDB**

```bash
docker compose up -d
```
3.**Run the entity creation script**

```bash
chmod +x create-entities.sh
./create-entities.sh
```
📡 NGSI-v2 API Used
We use the APPEND action to create multiple entities in Orion:
```bash
http
POST /v2/op/update
With a payload that defines entity types, attributes, and relationships in JSON format.
```

🧠 Example Entities
```bash
University ➝ urn:ngsi-ld:University:univ001

Building ➝ urn:ngsi-ld:Building:eng001 (with partOf relationship)

Classroom ➝ urn:ngsi-ld:Classroom:CR101 (with locatedIn)

Professor ➝ urn:ngsi-ld:Professor:prof001 (with teachesIn)

Student ➝ urn:ngsi-ld:Student:std001 (with enrolledIn)
```

📁 Project Structure
```bash
university-digital-twin/
├── docker-compose.yml        # Orion + MongoDB setup
├── create-entities.sh        # Bash script to load entities
└── README.md                 # This file
```

🧑‍💻 Author
Created by Nermine Ezzine – feel free to fork, modify and contribute!

