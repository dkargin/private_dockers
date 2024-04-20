FROM tingoose/cuda-cmake:v0.5.1

RUN apt-get update && apt-get install -y \
    libglew-dev \
    libglfw3-dev \
    libglm-dev \
    clang lldb lld \    
    freeglut3-dev \
    libboost-python-dev 

RUN pip install jinja2 pyopengl pygame numpy xlsxwriter openpyxl pandas trimesh pyrender matplotlib

RUN git clone --depth 1 --branch v3.1.9 https://github.com/AcademySoftwareFoundation/Imath && \
    cmake -S Imath -B ./Imath-build -DCMAKE_BUILD_TYPE=Release -DPYTHON=ON && cmake --build ./Imath-build -j8 && \
    cmake --install ./Imath-build && rm -rf Imath-build Imath

RUN git clone --depth 1 --branch 1.8.6 https://github.com/alembic/alembic.git && \
    cmake -S alembic -B ./alembic-build -DCMAKE_BUILD_TYPE=Release -DUSE_TESTS=OFF -DUSE_PYALEMBIC=ON && cmake --build ./alembic-build -j8 && \
    cmake --install ./alembic-build && rm -rf alembic-build alembic
