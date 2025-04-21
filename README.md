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
Start Orion and MongoDB

bash
Copier
Modifier
docker compose up -d
Run the entity creation script

bash
Copier
Modifier
chmod +x create-entities.sh
./create-entities.sh
📡 NGSI-v2 API Used
We use the APPEND action to create multiple entities in Orion:

http
Copier
Modifier
POST /v2/op/update
With a payload that defines entity types, attributes, and relationships in JSON format.

🧠 Example Entities
University ➝ urn:ngsi-ld:University:univ001

Building ➝ urn:ngsi-ld:Building:eng001 (with partOf relationship)

Classroom ➝ urn:ngsi-ld:Classroom:CR101 (with locatedIn)

Professor ➝ urn:ngsi-ld:Professor:prof001 (with teachesIn)

Student ➝ urn:ngsi-ld:Student:std001 (with enrolledIn)

📁 Project Structure
bash
Copier
Modifier
university-digital-twin/
├── docker-compose.yml        # Orion + MongoDB setup
├── create-entities.sh        # Bash script to load entities
└── README.md                 # This file
🧩 To-Do / Future Ideas
Add IoT devices (sensors) to monitor classrooms

Add real-time data updates for attendance or schedules

Build a frontend to visualize entity relationships

Use NGSI-LD for linked data features

📜 License
MIT License

🧑‍💻 Author
Created by [Your Name] – feel free to fork, modify and contribute!

yaml
Copier
Modifier

---

Let me know if you want to add diagrams (entity-relationship), examples of query commands, or
