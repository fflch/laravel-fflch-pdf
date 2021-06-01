Regiões:

    content
    footer
    
Configuração:

    php artisan vendor:publish --provider="Barryvdh\DomPDF\ServiceProvider"
    php artisan vendor:publish --provider="Fflch\LaravelFflchPdf\LaravelFflchPdfServiceProvider"

Em config/dompdf.php:

    "enable_php" => true

No seu .env:

    FFLCHPDF_SETOR='Setor de Graduação'

No seu blade:

    @extends('laravel-fflch-pdf::main')
    
No controller:

    use PDF;
    $pdf = PDF::loadView('exemplo', [
        'var'    => $var,
    ]);
    return $pdf->download("exemplo.pdf");
