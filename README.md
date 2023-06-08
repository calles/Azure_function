# Azure_function
Azure_function_example

* Serverless = Sin servidor.
* Trigger = Disparadores o desencadenadores.

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


