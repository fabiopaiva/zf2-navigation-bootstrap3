zf2-navigation-bootstrap3
=========================

Partial Navigation for Zend Framework 2 and Bootstrap 3

Usage: 

    git clone https://github.com/fabiopaiva/zf2-navigation-bootstrap3/
    cd zf2-navigation-bootstrap3
    mkdir ~/project/module/YourNamespace/view/partial
    mv navigation.phtml ~/project/module/YourNamespace/view/partial/

In your layout view

    <?php echo $this->
        navigation('navigation')
        ->menu()
        ->setUlClass('nav navbar-nav')
        ->setPartial('partial/navigation.phtml'); 
    ?>
Example navigation:

    return array(
        'navigation' => array(
            'default' => array(
                array(
                    'label' => 'Home',
                    'route' => 'home',
                    'icon' => 'glyphicon glyphicon-home''
                ),
                array(
                    'label' => 'Home',
                    'route' => 'home',
                    'icon' => 'glyphicon glyphicon-home''
                ),
                array(
                    'uri' => '#',
                    'separator' => true
                ),
                array(
                    'label' => 'Home',
                    'route' => 'home',
                    'icon' => 'glyphicon glyphicon-home''
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
