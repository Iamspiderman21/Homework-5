# Homework-5
Route::get('/products', [ProductController::class, 'index'])->name('products.index');
Route::get('/products/create', [ProductController::class, 'create'])->name('products.create');
Route::get('/products/{product}/edit', [ProductController::class, 'edit'])->name('products.edit');

<!-- resources/views/products/index.blade.php -->

@extends('layouts.app') <!-- Si tienes una plantilla base, si no, omite esta línea -->

@section('content')
    <!-- Aquí va tu contenido actual de la vista index -->

    <!-- Agrega un botón "Agregar producto" -->
    <a href="{{ route('products.create') }}" class="btn btn-primary">Agregar producto</a>
@endsection
// app/Http/Controllers/ProductController.php

namespace App\Http\Controllers;

use Illuminate\Http\Request;

class ProductController extends Controller
{
    public function index()
    {
        return view('products.index');
    }

    public function create()
    {
        return view('products.create');
    }

    public function edit($product)
    {
        // Lógica para recuperar datos del producto, pero no devolvemos una vista
        // La vista de edición no se mostrará directamente desde el controlador
    }
}

