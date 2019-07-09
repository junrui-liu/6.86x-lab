# Use the latest Miniconda3 release
FROM continuumio/miniconda3

# Use bash as the default shell
SHELL ["/bin/bash", "-c"]

# Create the working dir
WORKDIR /6.86x

# Copy conda environment file to image
COPY environment.yml /6.86x

# Update conda
RUN conda update -y -n base -c defaults conda

# Create the 6.86x environment
RUN conda env create -f environment.yml

# Remove unnecessary file
RUN rm environment.yml

# Activate the 6.86x environment when bash is run
RUN echo "source activate 6.86x" > ~/.bashrc
ENV PATH /opt/conda/envs/env/bin:$PATH

# Expose Jupyter notebook port
EXPOSE 8888

# Run Jupyter Lab by default
CMD /opt/conda/envs/6.86x/bin/jupyter lab \
        --notebook-dir=projects \
        --ip='0.0.0.0' \
        --port=8888 \
        --NotebookApp.token='' \
        --NotebookApp.password='' \
        --no-browser \
        --allow-root