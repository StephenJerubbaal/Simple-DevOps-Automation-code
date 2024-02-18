# Simple-DevOps-Automation-code
import os

def build_image(image_name, dockerfile_path):
    """
    Build Docker image from the given Dockerfile.
    """
    os.system(f'docker build -t {image_name} {dockerfile_path}')

def run_container(image_name, container_name, port_mapping):
    """
    Run Docker container from the specified image.
    """
    os.system(f'docker run -d --name {container_name} -p {port_mapping} {image_name}')

def stop_container(container_name):
    """
    Stop Docker container.
    """
    os.system(f'docker stop {container_name}')
    os.system(f'docker rm {container_name}')

def main():
    # Docker image and container details
    image_name = 'web_app_image'
    container_name = 'web_app_container'
    port_mapping = '8080:80'

    # Path to Dockerfile
    dockerfile_path = '/path/to/Dockerfile'

    # Build Docker image
    build_image(image_name, dockerfile_path)

    # Run Docker container
    run_container(image_name, container_name, port_mapping)

    # Simulate application deployment (e.g., copy files to container, run database migrations, etc.)
    # ...

    # Stop Docker container
    stop_container(container_name)

if __name__ == "__main__":
    main()
