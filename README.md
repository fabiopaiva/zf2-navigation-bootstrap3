zf2-navigation-bootstrap3
=========================

Partial Navigation for Zend Framework 2 and Bootstrap 3

Usage: 

    git clone https://github.com/fabiopaiva/zf2-navigation-bootstrap3/
    cd zf2-navigation-bootstrap3
    mkdir ~/project/module/YourNamespace/view/partial
    mv navigation.phtml ~/project/module/YourNamespace/view/partial/

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
            ->setPartial('partial/navigation.phtml'); 
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
                    'label' => 'Home',
                    'route' => 'home',
                    'icon' => 'glyphicon glyphicon-home'
                ),
                array(
                    'uri' => '#',
                    'separator' => true
                ),
                array(
                    'label' => 'Home',
                    'route' => 'home',
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
