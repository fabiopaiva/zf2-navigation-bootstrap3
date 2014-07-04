zf2-navigation-bootstrap3
=========================

Partial Navigation for Zend Framework 2 and Bootstrap 3

Usage: 

    cd zf2project/module/Application/view/
    mkdir partial && cd partial
    git clone https://github.com/fabiopaiva/zf2-navigation-bootstrap3/

In your layout view

    <nav class="navbar navbar-default" role="navigation">
      <div class="container-fluid">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle" data-toggle="collapse" data-target="#zf2-navigation-bootstrap3-1">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="<?php echo $this->url('home');?>">Brand</a>
        </div>
        <div class="collapse navbar-collapse" id="zf2-navigation-bootstrap3-1">
        <?php echo $this->
            navigation('navigation')
            ->menu()
            ->setUlClass('nav navbar-nav')
            ->setPartial('partial/zf2-navigation-bootstrap3/navigation.phtml'); 
        ?>
        </div>
      </div>
    </nav>

Example navigation:

    return array(
      'navigation' => array(
        'default' => array(
            array(
                'label' => 'Home',
                'route' => 'home',
                'icon' => 'glyphicon glyphicon-home'
            ),
            array(
                'label' => 'Menu 2',
                'uri' => '#',
                'icon' => 'glyphicon glyphicon-home',
                'pages' => array(
                    array(
                        'label' => 'Submenu',
                        'uri' => '#',
                        'icon' => 'glyphicon glyphicon-home'
                    ),
                    array(
                        'uri' => '#',
                        'separator' => true
                    ),
                    array(
                        'label' => 'Another Submenu',
                        'uri' => '#',
                        'icon' => 'glyphicon glyphicon-home'
                    ),
                )
            ),
            array(
                'label' => 'Menu 3',
                'uri' => '#',
                'icon' => 'glyphicon glyphicon-home'
                ),
            ),
        ),
    );



Activate default navigation in an autoload config file:

    return array(
        'service_manager' => array(
            'factories' => array(
                'Navigation' => 'Zend\Navigation\Service\DefaultNavigationFactory',
            ),
        ),
    );
