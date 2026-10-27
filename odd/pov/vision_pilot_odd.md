<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width: 100%; border: 1px solid #666; text-align: left;">
  <!-- IN ODD Section -->
  <thead>
    <tr style="background-color: #b4c6e7; color: #000000; text-align: center">
      <th colspan="7" style="text-align: center;">IN ODD</th>
    </tr>
    <tr style="background-color: #d9e1f2; color: #000000; text-align: center">
      <th colspan="4" style="text-align: center;">CATEGORIES</th>
      <th style="text-align: center;">ATTRIBUTE</th>
      <th style="text-align: center;">VALUE</th>
      <th style="text-align: center;">COMMENT</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td rowspan="5"><b>scenery_elements</b></td>
      <td rowspan="5"><b>drivable_area</b></td>
      <td colspan="2"></td>
      <td>drivable_area_type</td>
      <td>• motorways_or_highways_or_interstates</td>
      <td></td>
    </tr>
    <tr>
      <td rowspan="3"><b>drivable_area_geometry</b></td>
      <td>horizontal_plane</td>
      <td>curvature</td>
      <td>[0.0 .. 0.0125] 1/m</td>
      <td>Reference: steep curve track of Horiba MIRA test track</td>
    </tr>
    <tr>
      <td>transverse_plane</td>
      <td>bank_angle</td>
      <td>[-1 .. 7] deg</td>
      <td>Reference: US interstate highways</td>
    </tr>
    <tr>
      <td>longitudinal_plane</td>
      <td>inclination_angle</td>
      <td>[-5.0 .. 5.0] deg</td>
      <td>Reference: US interstate highways</td>
    </tr>
    <tr>
      <td colspan="2"><b>drivable_area_lane_specification</b></td>
      <td>lane_marking</td>
      <td>• clear_lane_marking<br>• blurred_lane_marking</td>
      <td>If specific types of lane markings need to be explicitly indicated, the taxonomy needs to be extended.</td>
    </tr>
    </tbody>
</table>

<table border="1" cellpadding="6" cellspacing="0" style="border-collapse: collapse; width: 100%; border: 1px solid #666; text-align: left;">
    <!-- OUT OF ODD Section -->
    <thead>
        <tr style="background-color: #b4c6e7;  color: #000000; text-align: center">
          <th colspan="7" style="text-align: center;">OUT OF ODD</th>
        </tr>
        <tr style="background-color: #d9e1f2; color: #000000; text-align: center">
          <th colspan="4" style="text-align: center;">CATEGORIES</th>
          <th style="text-align: center;">ATTRIBUTE</th> 
          <th style="text-align: center;">VALUE</th> 
          <th style="text-align: center;">COMMENT</th>
        </tr>
    </thead>
    <tr>
      <td rowspan="2"><b>scenery_elements</b></td>
      <td colspan="3"></td>
      <td>temporary_drivable_area_structures</td>
      <td>• construction_site_detour<br>• road_work</td>
      <td></td>
    </tr>
    <tr>
      <td><b>drivable_area</b></td>
      <td colspan="2"><b>drivable_area_surface</b></td>
      <td>drivable_area_included_surface_condition</td>
      <td>• icy<br>• flooded<br>• standing_water<br>• snow_on_surface<br>• wet<br>• surface_contamination</td>
      <td></td>
    </tr>
    <tr>
      <td><b>dynamic_elements</b></td>
      <td colspan="3"><b>traffic_agents</b></td>
      <td>presence_of_special_vehicles</td>
      <td>• ambulances<br>• police_vehicles<br>• work_vehicles</td>
      <td></td>
    </tr>
    <tr>
      <td rowspan="3"><b>environmental_conditions</b></td>
      <td rowspan="2"><b>weather</b></td>
      <td colspan="2">rain</td>
      <td>rainfall_rate</td>
      <td>&gt; light_rain</td>
      <td></td>
    </tr>
    <tr>
      <td colspan="2"></td>
      <td>snowfall_visibility</td>
      <td>&lt; light_snow</td>
    </tr>
    <tr>
      <td colspan="3"><b>illumination</b></td>
      <td>illuminance</td>
      <td>&lt; 0.1 lux</td>
      <td>Reference: ~ full moon at night</td>
    </tr>
  </tbody>
</table>