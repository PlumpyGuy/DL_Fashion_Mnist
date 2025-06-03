"# DL_Fashion_Mnist"
Stworzona przeze mnie sieć wygląda następująco:

    Conv((3,3), 1=>32, pad=Flux.SamePad()),
    Flux.relu,
    BatchNorm(32),

    Conv((3,3), 32=>32, pad=Flux.SamePad()),
    Flux.relu,
    BatchNorm(32),
    Dropout(0.25),

    Conv((3,3), 32=>64, pad=Flux.SamePad()),
    Flux.relu,
    MaxPool((2,2)),
    Dropout(0.25),

    Conv((3,3), 64=>128, pad=Flux.SamePad()),
    Flux.relu,
    BatchNorm(128),
    Dropout(0.25),

    Flux.flatten,

    Dense(14*14*128, 512),
    Flux.relu,
    BatchNorm(512),
    Dropout(0.5),

    Dense(512, 128),
    Flux.relu,
    BatchNorm(128),
    Dropout(0.5),

    Dense(128, 10),
    Flux.softmax
