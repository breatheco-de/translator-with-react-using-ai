<!-- hide -->
# Crea un Traductor Multilingüe en React usando ChatGPT
<!-- endhide -->

<onlyfor saas=false withBanner="false">
## 🌱 ¿Cómo iniciar este proyecto?

No clones este repositorio porque vamos a utilizar una plantilla diferente.

Recomendamos abrir la plantilla de react utilizando una herramienta de aprovisionamiento como [Codespaces](https://4geeks.com/lesson/what-is-github-codespaces) (recomendado) o [Gitpod](https://4geeks.com/lesson/how-to-use-gitpod). Alternativamente, puedes [clonar el repositorio de GitHub](https://4geeks.com/how-to/github-clone-repository) en tu computadora local usando el comando `git clone`.

Este es el repositorio que necesitas abrir o clonar:

```
https://github.com/4GeeksAcademy/react-hello
```

> ⚠ ¡Necesitarás tener Node.js instalado si lo haces localmente, pero todo eso ya está instalado en Codespaces o Gitpod!
</onlyfor>

## 📝 Instrucciones

### Paso 1: Configura el Proyecto

- [ ] Configura el proyecto boilerplate desde la plantilla de React proporcionada.

- [ ] Sigue las instrucciones en el README del repositorio para configurar tu entorno de desarrollo.

### Paso 2: Obtén Acceso a la API de ChatGPT

- [ ] Regístrate para una cuenta en [OpenAI](https://www.openai.com/).

- [ ] Navega a la sección de API y obtén tu clave API para acceder a ChatGPT.

### Paso 3: Crea el Formulario de Traducción

- [ ] En tu aplicación React, crea un formulario donde los usuarios puedan ingresar el texto que desean traducir.

- [ ] Agrega un menú desplegable o selección donde los usuarios puedan elegir el idioma de destino.

### Paso 4: Conecta a la API de ChatGPT

- [ ] Utiliza la entrada del usuario para crear un prompt para la API de ChatGPT que realice la traducción.

- [ ] Realiza una solicitud a la API de ChatGPT cuando se envíe el formulario.

Ejemplo:

```jsx
  const handleTranslate = async ({ text, targetLanguage }) => {
    const prompt = `Translate the following text to ${targetLanguage}:\n\n"${text}"`;

    try {
      const response = await fetch('https://api.openai.com/v1/completions', {
        method: 'POST',
        headers: {
          'Authorization': `Bearer TU_CLAVE_API_DE_OPENAI`,
          'Content-Type': 'application/json',
        },
        body: JSON.stringify({
          model: 'text-davinci-003',
          prompt: prompt,
          max_tokens: 1000,
          temperature: 0,
        }),
      });

      const data = await response.json();
      const translation = data.choices[0].text.trim();
      setTranslatedText(translation);
    } catch (error) {
      console.error('Error al traducir el texto:', error);
    }
  };
```

> **Nota:** Recuerda reemplazar `'TU_CLAVE_API_DE_OPENAI'` con tu clave API real de OpenAI.

### Paso 5: Muestra el Texto Traducido

- [ ] Muestra el texto traducido devuelto por la API al usuario en tu aplicación React.

- [ ] Asegúrate de que la traducción se presente en un formato legible, posiblemente con estilos para mejorar la experiencia del usuario.

### Sección de Bonus

#### Características Adicionales para Practicar y Mejorar el Proyecto

1. **Selección de Idioma de Origen:** Permite a los usuarios seleccionar el idioma de origen del texto.

2. **Detección de Idioma:** Implementa detección automática del idioma para el texto de origen.

3. **Soporte para Múltiples Idiomas de Destino:** Agrega más opciones de idiomas para la traducción.

4. **Historial:** Mantén un historial de traducciones para que los usuarios puedan revisarlas.

5. **Manejo de Errores:** Agrega un manejo robusto de errores para gestionar errores de API, problemas de red o entradas inválidas.

6. **Estilización:** Mejora la apariencia de tu aplicación usando CSS o librerías de estilos como [Bootstrap](https://getbootstrap.com/) o [Material-UI](https://material-ui.com/).

7. **Accesibilidad:** Asegúrate de que tu aplicación sea accesible para todos los usuarios, incluyendo aquellos que usan lectores de pantalla.

¡Explora diferentes mejoras para hacer tu aplicación de traductor más interactiva y amigable para el usuario!
