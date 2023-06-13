# Azure_function
Azure_function_example

Código

    module.exports = async function (context, req) {

        context.log("Iniciando la función...");

        if(req.query.ciudad){

            let resultado
            switch(req.query.ciudad.toLowerCase()){
                case 'mexico':
                resultado = {'clima':'El clima es templado',
                             'ropa': 'se recomienda usar ropa ligera'};
                break;

                case 'honduras':
                resultado = {'clima':'El clima es caliente',
                             'ropa': 'se recomienda usar ropa ligera'}; 
                break;

                case 'guatemala':
                resultado = {'clima':'El clima es frio',
                             'ropa': 'se recomienda usar ropa ligera'};
                break;

                default:
                resultado = {'error':'no existe información para la ciudad'};
            }
            context.res = {
                body: JSON.stringify({'result':resultado})
            };
        }else{
        context.res = {
            body: JSON.stringify({'error':'No hay ciudad especificada...'})
            };
        }
    
    };
    
    https://faas-example.azurewebsites.net/api/HttpTrigger1?code=TdP6o_daU9Rt7Io8G0hDVXz-8BKOUAbPXp64miM1wFKsAzFuZYpHNA==&ciudad=mexico


