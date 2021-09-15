<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" content="IE=edge" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script type="module" src="https://unpkg.com/@google/model-viewer/dist/model-viewer.min.js"></script>
    <script>
        $(document).ready(function() {
            //const modelViewer = $("model-viewer");
            const modelViewer = document.querySelector("model-viewer");

            window.switchModel = (element, name) => {
                if (name === "Chair") {
                    modelViewer.src =
                        "https://modelviewer.dev/assets/ShopifyModels/Chair.glb";
                    $("model-viewer").removeAttr("autoplay");
                    $("model-viewer").removeAttr("animation-name");
                } else if (name === "Astronaut") {
                    modelViewer.src =
                        "https://modelviewer.dev/shared-assets/models/Astronaut.glb";
                    $("model-viewer").removeAttr("autoplay");
                    $("model-viewer").removeAttr("animation-name");
                } else if (name === "RobotExpressive") {
                    modelViewer.src =
                        "https://modelviewer.dev/shared-assets/models/RobotExpressive.glb";
                    $("model-viewer").attr("autoplay", "true");
                    $("model-viewer").attr("animation-name", "Running");
                }

                const slides = document.querySelectorAll(".slide");
                slides.forEach((element) => {
                    element.classList.remove("selected");
                });
                element.classList.add("selected");
            };

            /*document
                .querySelector(".slider")
                .addEventListener("beforexrselect", (ev) => {
                    // Keep slider interactions from affecting the XR scene.
                    ev.preventDefault();
                });*/
        });
    </script>
    <style>
        model-viewer {
            background-color: #eee;
            overflow-x: hidden;
            --poster-color: #eee;
            width: 400px;
            height: 500px;
            margin-left: auto;
            margin-right: auto;
            top: 15%;
            left: 3%;
        }
        
        .AR-btn {
            background-image: url(https://modelviewer.dev/assets/ic_view_in_ar_new_googblue_48dp.png);
            background-repeat: no-repeat;
            background-size: 20px 20px;
            background-position: 12px 50%;
            background-color: #fff;
            position: absolute;
            top: 15%;
            left: 50%;
            transform: translateX(-50%);
            white-space: nowrap;
            bottom: 132px;
            padding: 0px 16px 0px 40px;
            font-family: Roboto Regular, Helvetica Neue, sans-serif;
            font-size: 14px;
            color: #4285f4;
            height: 36px;
            line-height: 36px;
            border-radius: 18px;
            border: 1px solid #dadce0;
        }
        
        body {
            position: absolute;
            top: 0;
            bottom: 0;
            right: 0;
            left: 0;
            width: 95%;
            height: 95%;
        }
        
        .modelText {
            color: rgb(65, 3, 3);
        }
        
        .slider {
            width: 100%;
            text-align: center;
            overflow: hidden;
            position: absolute;
            left: 5px;
            bottom: 6px;
        }
        
        .slides {
            display: flex;
            overflow-x: auto;
            scroll-snap-type: x mandatory;
            scroll-behavior: smooth;
            -webkit-overflow-scrolling: touch;
        }
        
        .slide {
            scroll-snap-align: start;
            flex-shrink: 0;
            width: 100px;
            height: 100px;
            background-size: contain;
            background-repeat: no-repeat;
            background-position: center;
            background-color: rgba(33, 63, 235, 0.76);
            margin-right: 10px;
            border-radius: 10px;
            border: none;
            display: flex;
        }
        
        .slide.selected {
            border: 2px solid #01070f;
        }
        
        .slide:focus {
            outline: none;
        }
        
        .slide:focus-visible {
            outline: 1px solid #4285f4;
        }
    </style>
    <title>Model Viewer Demo</title>
</head>

<body>
    <!--<model-viewer ar ar-modes="webxr scene-viewer quick-look" src="https://modelviewer.dev/assets/ShopifyModels/Chair.glb" alt="A 3D model of an Astronaut" shadow-intensity="1" camera-controls>
        <button slot="ar-button" class="AR-btn">Activate AR</button>

        <div class="slider">
            <div class="slides">
                <button class="slide modelText selected" onclick="switchModel(this, 'Chair')">Chair</button>
                <button class="slide modelText" onclick="switchModel(this, 'Astronaut')">Astronaut</button>
                <button class="slide modelText" onclick="switchModel(this, 'RobotExpressive')">Robot Expressive</button>
            </div>
        </div>
    </model-viewer>-->
    <model-viewer ar ar-modes="webxr scene-viewer quick-look" shadow-intensity="1" src="https://raw.githubusercontent.com/Midnightfury/3Dmodels/main/gltfModels/LPSP_SmallStarfigher.gltf" alt="An animate 3D model of a robot" camera-controls>
    </model-viewer>
    <model-viewer ar ar-modes="webxr scene-viewer quick-look" shadow-intensity="1" src="https://github.com/Midnightfury/3Dmodels/blob/main/glbModels/ambulance.glb" alt="An animate 3D model of a robot" camera-controls>
    </model-viewer>
</body>

</html>