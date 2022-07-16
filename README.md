# bootstrap-5-vertical-tabs-responsive
bootstrap 5 vertical tabs responsive

first add css
```
<style>
        .responsive-tab-menu .nav-pills .nav-link.active,
        .responsive-tab-menu .nav-pills .show>.nav-link {
            color: unset;
        }

        @media (max-width: 767px) {

            .responsive-tab-content,
            .responsive-tab-menu {
                display: block !important;
            }

            .nav-pills.nav-tabs-dropdown,
            .nav-tabs-dropdown {
                border: 1px solid #dddddd;
                border-radius: 5px;
                overflow: hidden;
                position: relative;
            }

            .nav-pills.nav-tabs-dropdown::after,
            .nav-tabs-dropdown::after {
                content: "☰";
                position: absolute;
                top: 8px;
                right: 15px;
                z-index: 2;
                pointer-events: none;
            }

            .nav-pills.nav-tabs-dropdown.open a,
            .nav-tabs-dropdown.open a {
                position: relative;
                display: block;
            }

            /* .nav-pills.nav-tabs-dropdown.open>li.active>a,
            .nav-tabs-dropdown.open>li.active>a {
                background-color: #eeeeee;
            } */

            .nav-pills.nav-tabs-dropdown li,
            .nav-tabs-dropdown li {
                display: block;
                padding: 0;
                vertical-align: bottom;
            }

            .nav-pills.nav-tabs-dropdown>li>a,
            .nav-tabs-dropdown>li>a {
                position: absolute;
                top: 0;
                left: 0;
                margin: 0;
                width: 100%;
                height: 100%;
                display: inline-block;
                border-color: transparent;
            }

            .nav-pills.nav-tabs-dropdown>li>a:focus,
            .nav-tabs-dropdown>li>a:focus,
            .nav-pills.nav-tabs-dropdown>li>a:hover,
            .nav-tabs-dropdown>li>a:hover,
            .nav-pills.nav-tabs-dropdown>li>a:active,
            .nav-tabs-dropdown>li>a:active {
                border-color: transparent;
            }

            /* hh */
            .nav-pills.nav-tabs-dropdown>li>a.active,
            .nav-tabs-dropdown>li>a.active {
                display: block;
                border-color: transparent;
                position: relative;
                z-index: 1;
                background: #fff;
            }

            .nav-pills.nav-tabs-dropdown>li.active>a:focus,
            .nav-tabs-dropdown>li.active>a:focus,
            .nav-pills.nav-tabs-dropdown>li.active>a:hover,
            .nav-tabs-dropdown>li.active>a:hover,
            .nav-pills.nav-tabs-dropdown>li.active>a:active,
            .nav-tabs-dropdown>li.active>a:active {
                border-color: transparent;
            }
        }
    </style>

```
Create tabs section and add class 

```
.responsive-tab-menu
```

```
<div class="d-flex align-items-start responsive-tab-menu">
  ......
</div>
 ```
 
Create Tabs Menu

```

<ul class="nav flex-column nav-pills nav-tabs-dropdown me-3" id="v-pills-tab" role="tablist" aria-orientation="vertical">
    <li class="nav-item">
        <a class="nav-link text-start active" href="#" id="v-pills-home-tab" data-bs-toggle="pill"
            data-bs-target="#v-pills-home" role="tab" aria-controls="v-pills-home" aria-selected="true">Home</a>
    </li>
    <li class="nav-item">
        <a class="nav-link text-start" href="#" id="v-pills-profile-tab" data-bs-toggle="pill"
            data-bs-target="#v-pills-profile" role="tab" aria-controls="v-pills-profile"
            aria-selected="false">Profile</a>
    </li>
</ul>

```
Create tab content
```

<div class="tab-content responsive-tab-content" id="v-pills-tabContent">
    <div class="tab-pane fade show active" id="v-pills-home" role="tabpanel" aria-labelledby="v-pills-home-tab"tabindex="0">home</div>
    <div class="tab-pane fade" id="v-pills-profile" role="tabpanel" aria-labelledby="v-pills-profile-tab" tabindex="0">profile</div>
</div>

```
Add jQuery

```
<script>
    $('.nav-tabs-dropdown')
        .on("click", ".nav-link:not('.active')", function (event) {
            // alert('e');
            $(this).closest('ul').removeClass("open");
        })
        .on("click", ".nav-link.active", function (event) {
            // alert('e');
            $(this).closest('ul').toggleClass("open");
        });
</script>
```
Get Full Code 

```
index.html
```
