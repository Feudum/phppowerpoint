phppowerpoint
=============
# Laravel PHPPowerpoint Bundle

---

PHPPowerpoint is a library written in PHP that create powerpoint presentations.
No Windows operating system is needed for usage because the result are pptx files (Office Open XML) that can be opened by all major office software.

---

## Installation

Run this command on the CLI:

    php artisan bundle:install phppowerpoint

### Registering the Bundle

Place the following code in ``application/bundles.php``:


    'phppowerpoint'    => array(
        'auto'        => true
    )


### Usage ####

    $objPHPPowerPoint = new PHPPowerPoint();
		$currentSlide = $objPHPPowerPoint->getActiveSlide();
		$shape = $currentSlide->createDrawingShape();
		$shape = $currentSlide->createRichTextShape();
		$shape->setHeight(300);
		$shape->setWidth(600);
		$shape->setOffsetX(170);
		$shape->setOffsetY(180);
		$shape->getAlignment()->setHorizontal( PHPPowerPoint_Style_Alignment::HORIZONTAL_CENTER );
		$textRun = $shape->createTextRun('Thank you for using PHPPowerPoint!');
		$textRun->getFont()->setBold(true);
		$textRun->getFont()->setSize(60);
		$textRun->getFont()->setColor( new PHPPowerPoint_Style_Color( 'FFC00000' ) );
		$objWriter = PHPPowerPoint_IOFactory::createWriter($objPHPPowerPoint, 'PowerPoint2007');
		$objWriter->save(str_replace('.php', '.pptx', __FILE__));


More info about PHPPowerPoint , visit : http://phppowerpoint.codeplex.com/
