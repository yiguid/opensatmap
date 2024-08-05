---
layout: page
title: Dataset
permalink: /dataset/
---

<section class="section">
    <div class="container is-max-desktop has-text-centered">
      <h2 class="title is-3">OpenSatMap Dataset</h2>
      <div class="columns is-centered">
        <div class="column">
          <div class="content">
            <div class="content has-text-justified">
              <h3 class="title is-4"> Description</h3>
              The dataset contains 3,787 high-resolution satellite images with fine-grained annotations, covering
              diverse geographic locations and popular driving datasets.
              It can be used for large-scale map construction and downstream tasks like autonomous driving.
              The images are collected from Google Maps at level 19 resolution (0.3m/pixel) and level 20 resolution
              (0.15m/pixel), we denote them as OpenSatMap19 and OpenSatMap20, respectively.
              For OpenSatMap19, the images are collected from 8 cities in China, including Beijing, Shanghai, Guangzhou,
              ShenZhen, Chengdu, Xi'an, Tianjin, and Shenyang. There are 1806 images in OpenSatMap19.
              For OpenSatMap20, the images are collected from 18 countries, more than 50 cities all over the world.
              There are 1981 images in OpenSatMap20.
              The figure below shows the sampling areas of the images in OpenSatMap.
              <!-- 插入html -->
            <div class="columns is-centered">
              <iframe src="static/gps_points.html" width="800" height="550"></iframe>
            </div>
          
                For each image, we provide instance-level annotations and eight attributes for road structures,
                including
                lanes lines, curb and
                virtual lines.
                The instances in OpenSatMap images are annotated by experts in remote sensing and computer vision.
                We will continue to update the dataset, to grow in size and scope to reflect evolving real-world
                conditions.
         
              <h3 class="title is-4">Examples of Annotated Images</h3>

                These are two examples of annotated images from OpenSatMap20. 
                Or you can play it in the
                <a href="https://colab.research.google.com/github/bjzhb666/OpensatMap-demo">
                  <img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"></a>
                <!-- <a href="https://colab.research.google.com/github/bjzhb666/OpensatMap-demo">demo notebook</a>   -->
                to visualize the annotations by yourself.
     
              <div class="column">
                <div class="content">
                  <div class="columns is-centered">
                    <div class="column is-full-width">

                      <div class="image-compare shadow-md rounded mb-16">
                        <img src="static/images/singapore-onenorth_-1_-1_satvisual-ori.png" alt="" />
                        <img src="static/images/singapore-onenorth_-1_-1_satvisual-instance.png" alt="" />
                      </div>
                      <p>
                        <div class="container is-max-desktop has-text-centered">
                        <b>Example 1:</b> Annotated image from OpenSatMap20. The image is collected from Singapore Onenorth (nuScenes).
                      </div>
                      </p>
                      <div class="image-compare shadow-md rounded mb-16">
                        <img src="static/images/flyover2_0_0_sat.png" alt="" />
                        <img src="static/images/flyover2_0_0_satvisual-instance.png" alt="" />
                      </div>
                      <p>
                        <div class="container is-max-desktop has-text-centered">
                        <b>Example 2:</b> Annotated image from OpenSatMap20. The image contains a flyover and roundabout, which is complex.
                      </div>
                      </p>

                    </div>
                  </div>
                </div>
              </div>

              
              <h3 class="title is-4">Line Category and Attribute</h3>
              We use vectorized polylines to represent a line instance.
              We first categorize all lines into three categories: <b>curb, lane line</b>, and <b>virtual line</b>.
              A curb is the boundary of a road. Lane lines are those visible lines forming the lanes. A virtual line
              means that there is no lane line or curb here, but logically there should be a boundary to form a full
              lane. Please refer to the figure below for examples of these three categories.
              <!-- insert an image -->
              <p>
              <div class="columns is-centered has-text-centered">
                <img src="./static/images/category.jpg" width="80%">
              </div>
              </p>
              For each line instance, we provide eight attributes: <b>color, line type,number of lines, function,
                bidirection, boundary, shaded, clearness</b>.
              Specifically, they are:
              <ul>
                <li><b>Color</b>: The color of the line. It can be white, yellow, others or none.</li>
                <li><b>Line type</b>: The type of the line. It can be solid, thick solid, dashed, short dashed dotted,
                  others or none.</li>
                <li><b>Number of lines</b>: The number of the line. It can be single, double, others or none.</li>
                <li><b>Function</b>: The function of the line. It can be Chevron markings, no parking, deceleration
                  line, bus lane, tidal line,
                  parking space, vehicle staging area, guide line, changable line, lane-borrowing line, others or none.
                </li>
                <li><b>Bidirection</b>: Whether the line is bidirectional. It can be true or false.</li>
                <li><b>Boundary</b>: Whether the line is a boundary. It can be true or false.</li>
                <li><b>Shaded</b>: The degree of occlusion. It can be no, minor or major.</li>
                <li><b>Clearness</b>: The clearness of the line. It can be clear or fuzzy.</li>
              </ul>
              Note that there is no man-made visible line on curbs and virtual lines, so we annotate their colors,
              line types, numbers of lines, and functions as <i>none</i>.
              <h3 class="title is-4">Annotation Format</h3>
              The annotations are stored in JSON format. Each image is annotated with "image_width", "image_height", and
              a list of "lines" where the elements are line instances.
              Each line is annotated with "category", "points", "color", "line_type", "line_num", "function",
              "bidirection", "boundary", "shaded", and "clearness".
              <pre><code class="language-python">{"img_name": {
    "image_width": int,
    "image_height": int,
    "lines": [
        {
            "category": str,
            "points": [
                [float, float],
                [float, float],
                [float, float], 
                ...
            ],
            "color": str,
            "line_type": str,
            "line_num": str,
            "function": str,
            "bidirection": bool,
            "boundary": bool,
            "shaded": str,
            "clearness": bool
        },
        {
            "category": str,
            "points": [
                [float, float],
                [float, float],
                [float, float], 
                ...
            ],
            "color": str,
            "line_type": str,
            "line_num": str,
            "function": str,
            "bidirection": bool,
            "boundary": bool,
            "shaded": str,
            "clearness": bool
        },
        ...
        ]
  }
}</code></pre>
              <h3 class="title is-4">Meta data</h3>
              The meta data of GPS coordinates and image acquisition time are also provided. The meta data is stored in
              a JSON file.
              <pre><code class="language-python">{
    "img_name": [
      {
        "centerGPS": [float, float],
        "centerWorld": [float, float],
        "filename": str
      },
      {
        "centerGPS": [float, float],
        "centerWorld": [float, float],
        "filename": str
      },
      ...
    ]
    ...
  }</code></pre>
              <h3 class="title is-4"> Download</h3>
              OpenSatMap mini: <a href="https://drive.google.com/drive/folders/1zKs-GV2aNobLDl6E17hTqy2L_WpNPkSb?usp=sharing">Google Drive</a>.
              <!-- , <a href="">Baidu Drive</a>, <a href="">Tencent Drive</a> -->
              <p>
                The full dataset will be released soon.
              </p>
              
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>