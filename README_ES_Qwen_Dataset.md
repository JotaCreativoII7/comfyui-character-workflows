# Kimi01 con Qwen Image Edit 2511

Workflow independiente para crear una influencer IA consistente con los modelos ya instalados de Qwen Image Edit 2511. Solo genera imágenes.

## Diferencia importante

Qwen Image Edit necesita una imagen de entrada. La etapa 1 no parte de ruido puro: toma una foto fuente y la convierte en la identidad maestra de Kimi01.

## Etapa 1

1. En `ETAPA 1 - FOTO FUENTE`, carga un retrato adulto con rostro claro.
2. Mantén encendido `INTERRUPTOR 1 - MASTER ON/OFF`.
3. Mantén apagado `INTERRUPTOR 2 - DATASET ON/OFF`.
4. Ejecuta varias veces y selecciona la mejor maestra.

Salida:

`output/CharacterDataset_Qwen2511/Kimi01_AI_Influencer/00_MASTER/`

## Etapa 2

1. Carga la maestra aprobada en `ETAPA 2 - CARGAR MASTER Kimi01`.
2. Apaga el interruptor 1.
3. Enciende el interruptor 2.
4. Ejecuta una cola para generar las 15 imágenes.

Las ramas incluyen belleza, moda, selfies, rooftop, café, street style, fitness, producto, interiores, resort y campaña.

Salida:

`output/CharacterDataset_Qwen2511/Kimi01_AI_Influencer/01_DATASET_15_CONTENT_SHOTS/`

El workflow utiliza el modelo Qwen Image Edit 2511 FP8, Qwen 2.5 VL FP8, Qwen Image VAE y el LoRA Lightning de cuatro pasos ya descargado.

## Recursos y enlaces de descarga

El workflow utiliza exactamente estos cuatro archivos:

### Modelo de difusión Qwen Image Edit 2511 FP8

- Archivo: `qwen_image_edit_2511_fp8_e4m3fn.safetensors`
- Página del archivo: https://huggingface.co/xms991/Qwen-Image-Edit-2511-fp8-e4m3fn/blob/main/qwen_image_edit_2511_fp8_e4m3fn.safetensors
- Descarga directa: https://huggingface.co/xms991/Qwen-Image-Edit-2511-fp8-e4m3fn/resolve/main/qwen_image_edit_2511_fp8_e4m3fn.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\diffusion_models\`

### Encoder de texto Qwen 2.5 VL

- Archivo: `qwen_2.5_vl_7b_fp8_scaled.safetensors`
- Descarga directa: https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/text_encoders/qwen_2.5_vl_7b_fp8_scaled.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\text_encoders\`

### VAE de Qwen Image

- Nombre usado por el workflow: `Qwen_Image-VAE.safetensors`
- Descarga directa: https://huggingface.co/Comfy-Org/Qwen-Image_ComfyUI/resolve/main/split_files/vae/qwen_image_vae.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\vae\`

El archivo descargado se llama `qwen_image_vae.safetensors`. Para utilizar este JSON sin modificarlo, renómbralo a `Qwen_Image-VAE.safetensors`.

### LoRA Lightning de cuatro pasos

- Archivo: `Qwen-Image-Edit-2511-Lightning-4steps-V1.0-fp32.safetensors`
- Página oficial: https://huggingface.co/lightx2v/Qwen-Image-Edit-2511-Lightning/blob/main/Qwen-Image-Edit-2511-Lightning-4steps-V1.0-fp32.safetensors
- Descarga directa: https://huggingface.co/lightx2v/Qwen-Image-Edit-2511-Lightning/resolve/main/Qwen-Image-Edit-2511-Lightning-4steps-V1.0-fp32.safetensors
- Carpeta de destino: `D:\ComfyUI_windows_portable_nvidia\ComfyUI_windows_portable\ComfyUI\models\loras\`

Después de instalar archivos nuevos, reinicia ComfyUI o actualiza su lista de modelos. No es necesario modificar el workflow.