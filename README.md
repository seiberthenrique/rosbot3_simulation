# 🤖 **ROSbot3 Simulation**

Repositório principal desenvolvido durante a disciplina de **Robótica**, com foco em consolidar o **ambiente de simulação no ROS 2 + Gazebo**.

---

## 🧭 **Estrutura do Projeto**

📁 **src/**  
- **`rosbot3_description`** — modelo URDF completo do robô, incluindo sensores e suportes com dimensões reais.  
- **`ros_commons`** — macros e utilitários compartilhados (sensores, controlador *skid-steer*, layouts RQT).  
- **`rosbot3_gazebo`** — integração com o Gazebo: *launch files*, mundos e parâmetros de simulação.  

⚙️ **scripts/**  
Scripts utilitários para:  
- `setup.bash` — configurar ambiente  
- `make.sh` — compilar  
- `make_clean.sh` — limpar  
- `download_gazebo_models.sh` — baixar modelos do Gazebo  

📦 **Submódulos Git**  
Todos os pacotes são versionados também como **submódulos**, permitindo manutenção separada de cada componente.

---

## 🌟 **Destaques**

- 🛞 Macro **`skid_steer_controller`** no `ros_commons`, controlando as quatro rodas e publicando odometria direto no Gazebo.  
- 🎮 Painel **`rqt_steering`** integrado ao *launch* da simulação, permitindo testes manuais rápidos.  

---

## 🚀 **Como Usar**

### 🔧 1. Pré-requisitos
Instale `git` e `git-lfs`:
```bash
sudo apt install git git-lfs
```

### 📥 2. Clonar o projeto (com submódulos)
```bash
git clone --recurse-submodules git@github.com:seiberthenrique/rosbot3_simulation.git
```

### 🔄 3. Atualizar repositório existente
```bash
git pull --rebase --recurse-submodules
```

### 📦 4. Corrigir possíveis problemas com Git LFS
```bash
git submodule foreach git lfs pull
```

### 🧩 5. Inicializar submódulos manualmente
Se esqueceu de usar `--recurse-submodules`:
```bash
git submodule update --init --recursive
```

### 🏗️ 6. Baixar modelos do Gazebo
```bash
./scripts/download_gazebo_models.sh
```

### ⚙️ 7. Compilar o workspace
```bash
./scripts/make.sh
```

### 🔗 8. Compilação com links simbólicos (desenvolvimento)
```bash
./scripts/make.sh --symlink-install
```
💡 Útil para atualizar *launchers* e configurações sem recompilar tudo.

### 🧹 9. Limpar a build atual
```bash
./scripts/make_clean.sh
```

### 🌐 10. Carregar ambiente
```bash
source ./scripts/setup.bash
```

### 🕹️ 11. Iniciar simulação no Gazebo
```bash
ros2 launch rosbot3_gazebo start.launch
```
