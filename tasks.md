---
layout: page
title: Tasks
permalink: /tasks/
---

<section class="section">
    <div class="container is-max-desktop has-text-centered">
      <h2 class="title is-3">OpenSatMap Dataset</h2>
      <div class="columns is-centered">
        <div class="column">
          <div class="content">
            <div class="content has-text-justified">
              <h3 class="title is-4">Task</h3>
              <h3 class="title is-5">Overview</h3>
              We introduce two tasks using OpenSatMap. Task 1 is instance-level line detection from satellite images.
              Task 2 is satellite-enhanced online map construction for autonomous driving.
              We are welcome to any other tasks using OpenSatMap. Please contact us for more information.
              <h3 class="title is-5">Task 1: Instance-level Line Detection</h3>
              The aim of this task is to extract road structures from satellite images at the instance level.
              For each instance, we use polylines as the vectorized representation and pixel-level masks as the
              rasterized representation.
              <h3 class="title is-5">Task 2: Satellite-enhanced Online Map Construction</h3>
              We use satellite images to enhance online map construction for autonomous driving.
              Inputs are carema images of an autonomous vehicle and satellite images of the same area and outputs are
              vectorized map elements around the vehicle.
              <h3 class="title is-4">Code </h3>
              <li>
                <a href="https://github.com/bjzhb666/get_google_maps_image">Here</a> is our code for data acquisition. The code is based on the <a
                  href="https://github.com/mitroadmaps/roadtracer/tree/master/dataset">RoadTracer</a>. <br>
              </li>
              <li>
                <a href=""> Here</a> is our code for instance-level line detection. The code is based on the <a
                  href="https://github.com/open-mmlab/mmsegmentation/">MMsegmentation</a>. <br>
              </li>
              <li>
                <a href=""> S-HDmap</a> is our code for map construction. The code is based on the <a
                  href="https://github.com/xjtu-cs-gao/SatforHDMap">SatforHDMap</a>.
              </li>

              <h3 class="title is-4">Contact</h3>
              For any questions, please contact <a href="mailto:zhaohongbo2022@ia.ac.cn">Hongbo Zhao</a> and <a
                href="mailto:fanlue2019@ia.ac.cn">Lue Fan</a>.
              Or you can open an issue in the <a href="https://github.com/OpenSatMap/OpenSatMap.github.io">OpenSatMap
                GitHub repository</a>.
              <h3 class="title is-4">Acknowledgement</h3>
              Our baseline codes are based on the <a
                href="https://github.com/open-mmlab/mmsegmentation/">MMsegmentation</a> and <a
                href="https://github.com/xjtu-cs-gao/SatforHDMap">SatforHDMap</a>.
              Our data acquisition code is based on the <a
                href="https://github.com/mitroadmaps/roadtracer/tree/master/dataset">RoadTracer</a>.
              We thank the authors for their contributions.
            </div>
          </div>
        </div>
      </div>
    </div>
  </section>