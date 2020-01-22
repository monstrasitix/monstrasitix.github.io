<style>
body,
body *,
body *::before,
body *::after {
    box-sizing: border-box;
}

.flex {
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
}

.column {
    width: 33%;
    padding: 1em;
}

.box {
    display: flex;
    align-items: center;
    justify-content: center;
    flex-direction: column;
    height: 200px;
    background-color: rgba(0, 0, 0, .1);
}
.text-center {
    text-align: center;
}
</style>


<br><br><br>


<div class="text-center">

# Going Offline
## Synchronization Architecture for SalesRep

Aphix Software

</div>


<br><br><br>


## Vision

<div class="text-center box">

Developing an offline-first solution for sale representatives
<br>
which enables ERP management on the move

</div>



<br><br><br>


## Technologies


<div class="flex">
    <div class="column">
        <div class="box">
            <strong>React</strong>
            <p>Design System</p>
        </div>
    </div>
    <div class="column">
        <div class="box">
            <strong>Redux</strong>
            <p>State Management</p>
        </div>
    </div>
    <div class="column">
        <div class="box">
            <strong>Cordova</strong>
            <p>Native Wrapper/WebView</p>
        </div>
    </div>
    <div class="column">
        <div class="box">
            <strong>SQLite</strong>
            <p>Native Caching</p>
        </div>
    </div>
    <div class="column">
        <div class="box">
            <strong>PouchDB</strong>
            <p>Persistence Interface</p>
        </div>
    </div>
    <div class="column">
        <div class="box">
            <strong>...</strong>
        </div>
    </div>
</div>


<br><br><br>


<div class="text-center">

## Backend

</div>

Core system would persist ERP records into our own databse and expose an interface for communication. Such interface could be expanded and leveraged with various monitoring toolings.

We chose CouchDB to offload ERP data internally. Providing our own schema and facility for scalability.

Surelu while offline we cannot sync with external data sources nor
update our clients. But with that we retain the notion of single source of truth mantra which provides sence of integrity for our computations.


<br><br><br>


<div class="text-center">

## Syncrhonizing

</div>

We will be using CouchDB for our internal storage. And our clients will utilize PouchDB to synchronise with internal storage and offload some memory natively with SQLite.

With that our