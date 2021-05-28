Regiões:

    content
    footer

No seu blade:

    @extends('laravel-fflch-pdf::main')

No controller:

    use PDF;
    $pdf = PDF::loadView('exemplo', [
        'var'    => $var,
    ]);
    return $pdf->download("exemplo.pdf");