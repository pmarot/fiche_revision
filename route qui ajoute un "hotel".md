app.post('/add', function (req, res) {

    var monid = parseInt(req.body.donnee1);
    var name = req.body.donnee2;
    var image = req.body.donnee3;
    var mark = parseInt(req.body.donnee4);
    var secteur = parseInt(req.body.donnee5);
    var newvalues = { 'id': monid, 'Nom': name, 'img': image, 'id_secteur': secteur, 'Nb_etoiles': mark };


    MongoClient.connect(url, function (err, database) {
        if (err) throw err;
        var dbo = database.db("reservation");

        dbo.collection("hotels").insertOne(newvalues, function (err, result) {
            if (err) {
                res.send('error');
            }
            res.send('ok');
            console.log("1 document inserted");
            database.close();
        });
    });
    //on est gentil on repond
    // res.send("toto");
});
