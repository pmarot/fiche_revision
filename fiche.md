#Fonction pour ajouter un nouvel hôtel dans la database hotels

   ````javascript
    $('#ajouter').click(function (event) {
        var val1 = $('#insert-id-h').val();
        var val2 = $('#insert-name-hotel').val();
        var val3 = $('#insert-img-hotel').val();
        var val4 = $('#insert-mark-h').val();
        var val5 = $('#insert-secteur-hotel').val();


        $.ajax({
            url: 'http://localhost:' + port + '/add',
            type: 'POST',
            data: { donnee1: val1, donnee2: val2, donnee3: val3, donnee4: val4, donnee5: val5 },
            success: function (data) {
                console.log(data);
            },
            error: function (e) {
                console.error("erreur :", e);
            }
        });
    });
    ````
