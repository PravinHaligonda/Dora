For mesh preprocessing: (to ensure watertight 3D models)
    CLAY

Dataset:
    Objaverse (subset filtered)
    4,00,000 3D meshes

    filter: (to ensure training stability)
        low quality meshes with missing faces
        severe self-intersections

Training:
    32 A100 GPU's for 2 days
    batch size: 2048
    learning rate: 5e-5

Extras:
    Flash-Attention-v2
    Mixed-precision training with FP16
    Gradient checkpoint to optimize memory usage and training efficiency
    Parameter in sharp edge sampling,
    set N_desired = 16384 and r_R = 30
    Low threshold = 20
    High threshold = 200 (for canny edge detection)