FROM runpod/stable-diffusion:web-automatic-3.0.0

SHELL ["/bin/bash", "-c"]

ENV PATH="${PATH}:/workspace/stable-diffusion-webui/venv/bin"

WORKDIR /

RUN rm /workspace/v1-5-pruned-emaonly.ckpt
ADD nai.ckpt /
ADD nai.vae.pt /
ADD nai.yaml /
RUN pip install -U xformers
RUN pip install runpod

ADD handler.py .
ADD start.sh /start.sh
RUN chmod +x /start.sh

CMD [ "/start.sh" ]
