# Kimi01 — generación de imágenes para influencer IA

Workflow de Flux 2 Klein 9B dedicado exclusivamente a generar imágenes de Kimi01, una influencer virtual adulta, atractiva, fotorealista y comercial. No genera captions, archivos TXT ni otros documentos.

## Etapa 1: imagen maestra

Al importar el workflow, la etapa 1 está activa y las 15 salidas de la etapa 2 están desactivadas.

1. Ejecuta varias veces la etapa 1.
2. Selecciona una imagen frontal con identidad clara, ojos definidos, piel natural y cabello consistente.
3. Copia la imagen elegida a la carpeta `input` de ComfyUI.

Salida:

`output/CharacterDataset/Kimi01_AI_Influencer/00_MASTER/`

## Etapa 2: 15 imágenes de contenido

1. Carga la imagen maestra en el nodo `LoadImage` de la etapa 2.
2. Desactiva el nodo `SaveImage` de la etapa 1.
3. Activa los 15 nodos `SaveImage` de la etapa 2.
4. Ejecuta una cola para generar las 15 tomas.

Las imágenes incluyen retrato de belleza, moda, selfie natural, selfie frente al espejo, rooftop, café, street style, fitness, presentación de producto, interior de lujo, resort, ángulo bajo, ángulo alto, primer plano riendo e imagen de campaña.

Salida:

`output/CharacterDataset/Kimi01_AI_Influencer/01_DATASET_15_CONTENT_SHOTS/`

## Control de calidad

Conserva únicamente imágenes donde Kimi01 sea claramente la misma persona. Descarta cambios de rostro, edad, ojos, pecas, lunar, cabello o proporciones; manos incorrectas; extremidades duplicadas; texto; logotipos; piel artificial y anatomía defectuosa.

El workflow solo guarda archivos de imagen mediante nodos `SaveImage` estándar de ComfyUI.
## Interruptores de las dos etapas

El workflow incluye dos controles visuales `Fast Groups Bypasser`:

- `INTERRUPTOR 1 - ETAPA MAESTRA ON/OFF`: controla únicamente `KIMI01_STAGE_1_MASTER`.
- `INTERRUPTOR 2 - DATASET 15 IMAGENES ON/OFF`: controla únicamente `KIMI01_STAGE_2_DATASET`.

Estado inicial recomendado:

- Etapa maestra: ON.
- Dataset de 15 imágenes: OFF.

Después de obtener y cargar la imagen maestra, apaga el interruptor 1 y enciende el interruptor 2. No es necesario activar o desactivar manualmente los 15 nodos `SaveImage`.
## Recursos y enlaces de descarga

El workflow utiliza exactamente estos tres archivos:

### Modelo de difusión

- Archivo: `flux-2-klein-9b.safetensors`
- Descarga oficial: https://huggingface.co/black-forest-labs/FLUX.2-klein-9B/blob/main/flux-2-klein-9b.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\diffusion_models\`

El repositorio oficial de Black Forest Labs está protegido por licencia. Inicia sesión en Hugging Face, acepta las condiciones del repositorio y después descarga el archivo.

### Encoder de texto Qwen 3 8B

- Archivo: `qwen_3_8b_fp8mixed.safetensors`
- Descarga directa: https://huggingface.co/Comfy-Org/flux2-klein-9B/resolve/main/split_files/text_encoders/qwen_3_8b_fp8mixed.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\text_encoders\`

### VAE de Flux 2

- Archivo: `flux2-vae.safetensors`
- Descarga directa: https://huggingface.co/Comfy-Org/flux2-dev/resolve/main/split_files/vae/flux2-vae.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\vae\`

Después de instalar archivos nuevos, reinicia ComfyUI o actualiza su lista de modelos. No es necesario modificar el workflow.