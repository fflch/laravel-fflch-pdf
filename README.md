## Conceito
[<img src="/images/logo-fflch.png" width="80"/>](/images/logo-fflch.png)

Biblioteca padronizada para modelo de PDF da FFLCH

## Regiões:
- content
- footer
    
## Configuração e  Uso:

- Faça a publicação das configurações base
    php artisan vendor:publish --provider="Barryvdh\DomPDF\ServiceProvider"
    php artisan vendor:publish --provider="Fflch\LaravelFflchPdf\LaravelFflchPdfServiceProvider"


- Em config/dompdf.php:
    "enable_php" => true

- No seu .env:
    FFLCHPDF_SETOR='Setor de Graduação'

- No seu blade:
    @extends('laravel-fflch-pdf::main')
    
- No controller:
    use PDF;
    $pdf = PDF::loadView('exemplo', [
        'var'    => $var,
    ]);
    return $pdf->download("exemplo.pdf");

- Caso queira personalizar o nome do setor, antes de efetuar o loadView, adicione a seguinte linha ao seu controller

    config(['laravel-fflch-pdf.setor' => "Seção Técnica de Informática"]);

- Caso seu arquivo tenha múltiplas páginas, não se esqueça de adicionar a quebra de linha
    <p class="page-break"></p> 

