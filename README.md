# prototype
<!DOCTYPE html>

<html>
<head>
<link href="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/css/bootstrap.min.css" rel="stylesheet"/><title>Fruit Tracker</title>
<script src="https://cdn.jsdelivr.net/npm/web3@4.1.1/dist/web3.min.js"></script>

<style>
    body {
        background-color: #f4f4f4;
    }
    .container {
        background-color: white;
        padding: 20px;
        border-radius: 5px;
        box-shadow: 0px 0px 10px rgba(0, 0, 0, 0.1);
    }
    .navbar {
        margin-bottom: 20px;
    }
</style>
</head>
<body>
<div class="container mt-4">
<nav class="navbar navbar-expand-lg navbar-light bg-light">
<a class="navbar-brand" href="#">Fruit Tracker</a>
<button aria-controls="navbarNav" aria-expanded="false" aria-label="Toggle navigation" class="navbar-toggler" data-target="#navbarNav" data-toggle="collapse" type="button">
<span class="navbar-toggler-icon"></span>
</button>
<div class="collapse navbar-collapse" id="navbarNav">
<ul class="navbar-nav">
<li class="nav-item active">
<a class="nav-link" href="#">Home <span class="sr-only">(current)</span></a>
</li>
</ul>


</div>
</nav>
<button class="btn btn-primary mt-3" onclick="connect()">Connect to MetaMask</button>
<h1>Fruit Tracker</h1>
<div id="transactionInfo">
<p>Transaction Hash: <span id="transactionHash"></span></p>
<p>Transaction Status: <span id="transactionStatus"></span></p>
</div>
<!-- Harvest -->

<form class="mb-3">
<input class="form-control mt-2" id="fruitType" placeholder="Fruit Type" type="text"/>
<input class="form-control mt-2" id="harvestDate" placeholder="Harvest Date" type="number"/>
<input class="form-control mt-2" id="quantity" placeholder="Quantity" type="number"/>
<button class="btn btn-success mt-2" id="harvestButton" type="submit">Harvest</button>
</form>
<!-- Packaging -->

<form class="mb-3">
<input class="form-control mt-2" id="batchId" placeholder="Batch ID" type="number"/>
<input class="form-control mt-2" id="date" placeholder="Date" type="number"/>
<input class="form-control mt-2" id="conditions" placeholder="Conditions" type="text"/>
<button class="btn btn-success mt-2" id="packageButton" type="submit">Package</button>
</form>
<!-- Transportation -->

<form class="mb-3">
<input class="form-control mt-2" id="transportBatchId" placeholder="Batch ID" type="number"/>
<input class="form-control mt-2" id="departureTime" placeholder="Departure Time" type="number"/>
<input class="form-control mt-2" id="estimatedArrivalTime" placeholder="Estimated Arrival Time" type="number"/>
<button class="btn btn-success mt-2" id="transportButton" type="submit">Transport</button>
</form>
<!-- Arrival -->

<form class="mb-3">
<input class="form-control mt-2" id="arrivalBatchId" placeholder="Batch ID" type="number"/>
<input class="form-control mt-2" id="actualArrivalTime" placeholder="Actual Arrival Time" type="number"/>
<input class="form-control mt-2" id="condition" placeholder="Condition" type="text"/>
<button class="btn btn-success mt-2" id="confirmArrivalButton" type="submit">Arrival</button>
</form>
<!-- Sale -->

<form class="mb-3">
<input class="form-control mt-2" id="sellBatchId" placeholder="Batch ID" type="number"/>
<input class="form-control mt-2" id="saleDate" placeholder="Sale Date" type="number"/>
<input class="form-control mt-2" id="price" placeholder="Price" type="number"/>
<button class="btn btn-success mt-2" id="sellButton" type="submit">Sell</button>
</form>
<!-- Consumer Feedback -->

<form class="mb-3">
<input class="form-control mt-2" id="feedbackBatchId" placeholder="Batch ID" type="number"/>
<input class="form-control mt-2" id="feedback" placeholder="Feedback" type="text"/>
<button class="btn btn-success mt-2" id="feedbackButton" type="submit">Feedback</button>
</form>
<script src="https://cdn.jsdelivr.net/npm/web3@4.1.1/dist/web3.min.js"></script>
<script src="web3.js"></script>
</div>
<script src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script><script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.5.2/js/bootstrap.min.js"></script>
<script>
    function expandSection(sectionName) {
        var containers = document.querySelectorAll('.action-container');
        containers.forEach(function(container) {
            if (container.contains(document.querySelector('h2:contains(' + sectionName + ')'))) {
                container.querySelector('form').style.display = 'block';
            } else {
                container.querySelector('form').style.display = 'none';
            }
        });
    }

    function collapseSection(sectionName) {
        var container = document.querySelector('.action-container h2:contains(' + sectionName + ')').parentElement;
        container.querySelector('form').style.display = 'none';
    }
</script>
</body>
</html>
