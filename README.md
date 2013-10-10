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
