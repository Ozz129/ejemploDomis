# ejemploDomis


SERVER:JS

const express = require('express');
const app = express();
const managerRouter = require('./managerRouter')

app.use(express.json())

app.get("/ruta", (req, res)=>{
    res.status(404).send('Hola, bienvenido a mis domicilios')
})

app.use('/api', managerRouter)

app.listen(3000, ()=>{
    console.log("servidor abierto")
}
)



MANAGERROUTER.JS

const express = require('express');
const router = express.Router();


router.post("/manager", (req, res)=>{

    const body = req.body

    res.status(200).send({
        headers:"",
        message: "Administrador creado exitosamente",
        body
    })

})
router.get("/manager/:id", (req, res)=>{

    res.status(200).send({
        headers:"",
        message: "Lista de managers",
        body: req.params
    })
})

module.exports = router;
