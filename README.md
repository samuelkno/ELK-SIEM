# ELK Stack – Configuración de usuarios

Este laboratorio utiliza Elasticsearch, Logstash y Kibana con seguridad habilitada.  
A continuación, se detallan los comandos necesarios para crear los usuarios requeridos dentro del contenedor de **Elasticsearch**.

---

## 🔹 Paso 1 – Acceder al contenedor

```bash
docker exec -it elasticsearch bash
🔹 Paso 2 – Crear usuarios del sistema
Dentro del contenedor, ejecuta los siguientes comandos:

bash
Copiar código
bin/elasticsearch-users useradd kibana_system_user -p Alejandro93 -r kibana_system
bin/elasticsearch-users useradd logstash_internal -p Alejandro93 -r logstash_system
bin/elasticsearch-users useradd admin_lab -p Alejandro93 -r superuser
🔹 Notas
Puedes cambiar los nombres de usuario (kibana_system_user, logstash_internal, admin_lab)
por los que prefieras.

También puedes modificar la contraseña (Alejandro93) para mayor seguridad.

El usuario admin_lab es el que utilizarás para iniciar sesión en Kibana
y administrar el entorno.

Los usuarios kibana_system_user y logstash_internal son cuentas de servicio internas,
utilizadas por los contenedores de Kibana y Logstash respectivamente.

💡 Consejo: después de crear los usuarios, puedes verificar que se hayan registrado con:

bash
Copiar código
bin/elasticsearch-users list
yaml
Copiar código

---

¿Deseas que te lo agregue con formato más visual tipo “documentación de laboratorio”

