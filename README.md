#  Amount in Words
# Installation

You can install the package via Composer. Run the following command in your Laravel project's root directory:

```bash
composer require jitup1/amountinwords

Usage
'providers' => [
    // Other Service Providers

    jitup1\amountinwords\AmountinwordsServiceProvider::class,
],



<?php

namespace App\Http\Controllers;

use jitup1\amountinwords\PrintAmountInWords;

class AmountController extends Controller
{
    protected $amountInWords;

    public function __construct(PrintAmountInWords $amountInWords)
    {
        $this->amountInWords = $amountInWords;
    }

    public function index()
    {
        $amount = 12345; // Example amount
        $words = $this->amountInWords->displayWords($amount);

        return response()->json([
            'amount' => $amount,
            'in_words' => $words,
        ]);
    }
}
Step 3: Create a Route
You can create a route to access the controller in your routes/web.php (or routes/api.php) file:

use App\Http\Controllers\AmountController;

Route::get('/amount-in-words', [AmountController::class, 'index']);

Usage
   $amount = 4000.00; // Example amount
    // Call the correct method to convert amount to words with currency names
    $words = $this->amountInWords->amountToWords($amount, 'USD', 'cents');

    return response()->json([
        'amount' => $amount,
        'in_words' => $words,


Author
jitup123
Email: patel.jitendra.jitu@gmail.com


