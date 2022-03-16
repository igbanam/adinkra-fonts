<script>
  export let name
  export let icon_color
</script>

<div class="preview">
  <span class="inner" style="color: {icon_color};">
    <i class="adk adk-{name}"></i>
  </span>
  <br>
  <span class='label'>{name}</span>
</div>

<style>
  .preview {
    width: 100px;
    display: inline-block;
    margin: 10px;
  }
  .preview .inner {
    display: inline-block;
    width: 100%;
    text-align: center;
    background: #f5f5f5;
    -webkit-border-radius: 3px 3px 0 0;
    -moz-border-radius: 3px 3px 0 0;
    border-radius: 3px 3px 0 0;
  }
  .preview .inner  {
    line-height: 85px;
    font-size: 40px;
  }
  .label {
    display: inline-block;
    width: 100%;
    box-sizing: border-box;
    padding: 5px;
    font-size: 10px;
    font-family: Monaco, monospace;
    color: #666;
    white-space: nowrap;
    overflow: hidden;
    text-overflow: ellipsis;
    background: #ddd;
    -webkit-border-radius: 0 0 3px 3px;
    -moz-border-radius: 0 0 3px 3px;
    border-radius: 0 0 3px 3px;
    color: #666;
  }
</style>
