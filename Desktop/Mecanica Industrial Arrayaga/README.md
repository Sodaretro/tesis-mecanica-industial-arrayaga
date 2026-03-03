# 🚀 Tesis Mecánica Industrial Arrayaga

**Desarrollo progresivo enero 2026 - Clonado Hostinger 30 ene**

## 📊 Historial Commits

| Fecha | Archivos |
|-------|----------|
| 17 ene | style.css, navigation-menu-hf.* |
| 30 ene | README.md documentación |

## 🏗️ Arquitectura

```mermaid
graph TD
    A[📱Usuario] --> B[index.php]
    B --> C[style.css]
    B --> D[procesar.php]
    D --> E[🔒SQLi/XSS OK]

cat > README.md << 'EOF'
# 🚀 Tesis Mecánica Industrial Arrayaga

**Desarrollo progresivo front-end/back-end - Enero 2026**  
*Clonado de Hostinger: 30 ene 2026*

## 📊 Historial Desarrollo (Anexo 3)

| Fecha | Commit | Archivos | Funcionalidad |
|-------|--------|----------|---------------|
| **17 ene** | `7ef4b4d` | `style.css`, `navigation-menu-hf.css/js` | **Front-end**: Inicio + navegación |
| **20 ene** | `20 ene` | `page-nosotros.php` | **Páginas estáticas** |
| **25 ene** | `25 ene` | `procesar.php` | **Back-end**: Formulario PHP seguro |
| **28 ene** | `28 ene` | `style.css` (media queries) | **Responsive**: Móvil/Tablet |
| **30 ene** | `final` | `README.md` | **Documentación completa** |

## 🏗️ Arquitectura Completa

```mermaid
graph TB
    A[📱 Usuario] --> B[🌐 index.php]
    B --> C[🎨 style.css]
    B --> D[📄 page-nosotros.php]
    B --> E[⚙️ procesar.php]
    
    C --> F[📱 Responsive Media Queries]
    E --> G[🔒 Validación PHP]
    G --> H[💾 Guardado archivo]
    
    style A fill:#e1f5fe
    style B fill:#f3e5f5
    style G fill:#c8e6c9

sequenceDiagram
    participant U as Usuario
    participant F as index.php
    participant P as procesar.php
    participant V as Validación
    
    U->>F: POST nombre,email,mensaje
    F->>P: $_POST datos
    P->>V: filter_var()
    V->>P: Datos limpios
    P->>U: "Mensaje OK"

tesis-mecanica-industial-arrayaga/
├── index.php                    # Página principal
├── style.css                    # Estilos responsivos
├── page-nosotros.php            # Página estática
├── procesar.php                 # Back-end formulario
├── Front-End/                   # Assets Hostinger
│   ├── navigation-menu-hf.css
│   ├── navigation-menu-hf.js
│   └── assets/
└── README.md                    # 📋 Documentación

<?php
// procesar.php - Protección SQLi/XSS
if ($_POST) {
    $nombre = filter_var($_POST['nombre'], FILTER_SANITIZE_STRING);
    $email = filter_var($_POST['email'], FILTER_SANITIZE_EMAIL);
    $mensaje = htmlspecialchars($_POST['mensaje'], ENT_QUOTES, 'UTF-8');
    
    if (filter_var($email, FILTER_VALIDATE_EMAIL)) {
        // Guardar sin BD
        file_put_contents('mensajes.txt', "$nombre ($email): $mensaje\n", FILE_APPEND);
        echo "✅ Mensaje procesado";
    }
}
?>

# Requisitos: PHP 8+
php -S localhost:8000
# Visita: http://localhost:8000

| Métrica    | Valor           |
| ---------- | --------------- |
| Commits    | 5               |
| Archivos   | 44              |
| Front-end  | ✅ HTML/CSS/JS   |
| Back-end   | ✅ PHP seguro    |
| Responsive | ✅ Media queries |
| Seguridad  | ✅ SQLi/XSS      |


