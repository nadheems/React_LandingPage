# Landing Page Template com React JS e Material UI :dart:

Site: https://hbsales.onrender.com/

![link Home do site](https://raw.githubusercontent.com/alessandradocouto/landing-page-template-reactjs/master/src/assets/Home.png)


![link About do site](https://raw.githubusercontent.com/alessandradocouto/landing-page-template-reactjs/master/src/assets/About.png)

![link Contact do site](https://raw.githubusercontent.com/alessandradocouto/landing-page-template-reactjs/master/src/assets/Contact.png)



## Índice

- [Sobre](https://github.com/alessandradocouto/landing-page-template-reactjs#sobre)
- [Aprendizados](https://github.com/alessandradocouto/landing-page-template-reactjs#aprendizados)
- [Dependências](https://github.com/alessandradocouto/landing-page-template-reactjs#dependências)



## Sobre

Landing page Template em React JS feita para desenvolvedores/designs que querem criar rapidamente uma landing page profissional para seus projetos open source. 


## Aprendizados

:heavy_check_mark: React Router v6+ no DOM

No App.js

`import {BrowserRouter, Routes, Route} from react-router-dom';`
 
O componente **Navbar** tem elementos que se repetem em todas as páginas e tem elementos que estão em 'Routes', logo fica dentro de 'BrowserRouter'.

```
<BrowserRouter>
    <Navbar />
    <Routes>
        <Route path='/' element={<Home />} />
        <Route path='/about' element={<About />} />
        <Route path='/contact' element={<Contact />} />
    </Routes>
</BrowserRouter>
```

Dentro da pasta pages :file_folder: e no arquivo :page_with_curl: Home.js

```
const Home = () => {
  return (
    <>
    <Header />
    <GetStarted />
    <GetInTouch />
    </>

  )
}
```


Dentro do componente **Navbar**:

```
import { Link } from 'react-router-dom';

const itemList = [
    {
      text: "Home",
      to: "/" 
    },
    {
      text: "About",
      to: "/about"
    },
    {
        text: "Contact",
        to: "/contact"
    }
];


const Navbar = () => {
    
    return (
        <AppBar 
        component="nav" 
        position="sticky"
        sx={{ 
            backgroundColor: 'orange', 
        }}
        elevation={0}
        >
            <StyledToolbar>
                <Typography
                variant="h6"
                component="h2"

                >
                    HBSales
                </Typography>
                
                <ListMenu>
                    {itemList.map( ( item ) => {
                        const { text } = item;
                        return(
                            <ListItem key={text}>
                                <ListItemButton component={Link} to={item.to}
                                sx={{
                                    color: '#fff',
                                    "&:hover": {
                                        backgroundColor: 'transparent',
                                        color: '#1e2a5a',
                                    }
                                }}
                                >
                                    <ListItemText primary={text} />
                                </ListItemButton>
                            </ListItem>
                        )
                    })}
                </ListMenu>
            </StyledToolbar>
        </AppBar>
    )
}

export default Navbar;
```



:heavy_check_mark: Utilização de sx e breakpoints em Material UI

O que é [sx](https://mui.com/system/getting-started/the-sx-prop/)?

A propriedade sx permite que você trabalhe com um superconjunto de CSS que empacota todas as funções de estilo expostas em @mui/system. Você pode especificar qualquer CSS válido usando este suporte, bem como muitas propriedades com reconhecimento de tema que são exclusivas do MUI System.


```
<Box component='article'>
    sx={{
        px: 4,
    }}
</Box>


<Grid item xs={12} sm={4} md={6}>
    sx={{
        order: {xs: 4, sm: 4, md: 3}
    }}
</Grid>
```


:heavy_check_mark: Uso de Componentes reutilizáveis em React;

Conteúdo do componente Title:

```
import { Typography } from '@mui/material'
import React from 'react'

const Title = ({ text, textAlign }) => {
  return (
    <Typography 
    variant='h4'
    component='h3'
    sx={{ 
      fontWeight: '700',
      textAlign: textAlign,
   }}
    >
      {text}
    </Typography>
  )
}

export default Title;
```


:heavy_check_mark: Utilização de Styled-Components com Material UI




`npm run build`

### Testar aplicação:

`npm test`
