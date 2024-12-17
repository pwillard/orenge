# Train Engineer for Blender and Open Rails

Based on the 3D Canvas Train Engineer by Paul Gausden.

Changes: Use wheel diameter instead of radius.
        

## Introduction

* Only build high poly wheels
* use pre-made shapes for the wheels
* Can probably rely on default animation with OpenRails Exporter

* Future: Spoked Wheels


## Outline code

1. Import Libraries
2. Pre-Load Constant Data
3. Define Functions
4. Get User Input
5. Select Appropriate model vector containers
6. Position main components
7. generate results

A. Import Libraries: We will only need the default `BPY` library for this project at the moment.

B. Pre-Load Constant and variableData: 

    We will pre-load the constant data such as the list of models, the list of features, and the list of target variables.

    Constants:
    STDGAUGE = 1.435
    SCALE_FACTOR = 0.3048
    SCALE_SETTING = 1.0
    WHEEL_FACETS = 32
    # USE PRESETS?
    WHEEL_40 = 1.016
    WHEEL_36 = 0.9144
    WHEEL_33 = 0.8382
    WHEEL_28 = 0.7174
    


    Variables:
    wheelThickness
    wheelDiameter  - preset to 0.8382 # 33 inches in metric

C. Define the Objects we will produce:
    Wheel
    Axles
    Body
    Under-Carriage

D. Define Functions: We will define the functions that will be used in the project.

Set Metric or Imperial:

```
    def set_unit_system(use_metric=True, scale=1.0):
    """
    Set the unit system and scale factor in Blender.

    Args:
        use_metric (bool): True for Metric, False for Imperial.
        scale (float): Scale factor to apply.
    """
    scene = bpy.context.scene
    unit_settings = scene.unit_settings

    if use_metric:
        unit_settings.system = 'METRIC'
        unit_settings.scale_length = scale
        print(f"Unit System set to Metric with scale {scale}")
    else:
        unit_settings.system = 'IMPERIAL'
        unit_settings.scale_length = scale
        print(f"Unit System set to Imperial with scale {scale}")
```
GET USER INPUT:

```
    def get_user_input():
    """
        Get user input for wheel thickness, wheel diameter, and wheel type, Metric or Imperial, bogie or non-bogie, and number of wheels.
        Bogies will have a different axle configuration, get axle offset from bogie center
        Number of wheels will be used to determine the number of axles.
    """
```

    def select_appropriate_model_vector_containers():

    def generate_results():

    def generate_wheel_vector():
        Create custom wheel profile shape and multiply by scale factor
    
    def generate_axle_vector():
        Create cylinder shape and multiply by scale factor
    
    def generate_body_vector():
        Create box shape and multiply by scale factor
    
    def generate_undercarriage_vector():
        Create box shape and multiply by scale factor

    def set_position():

    def set_child_of():


