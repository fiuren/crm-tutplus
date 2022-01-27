# CRM en WordPress

**No seguinte proxecto, e seguindo os pasos do tutorial de : https://code.tutsplus.com/tutorials/create-a-simple-crm-in-wordpress-using-custom-capabilities--cms-22985, imos a crear un CRM ou complemento para WordPress, o cal terá como función administrar funcións como escoller quen pode entrar como administrados e quen coma simple usuario ou outros modos. É dicir, poder restrinxir o acceso de usuarios a partes da interfaz da administración de WordPress**

**Dito complemento, traballará no apartado de Contactos, onde se almacenará a información dos usuarios que se inserten, e no cal poderemos filtrar segundo distintos parámetros (Email, número de telefono, fotos, data...) que se poden aumentar o diminuir segundo queiramos, sempre e cando se realice dende a parte de administración. Eses parámetros ou campos persoalizados os introduciremos na parte de "Usuarios" que se encontra só se se entra como administrador. Doutro xeito solo se poderán consultar os datos que se encontren no apartado de Contactos.**

**O código do complemento de WordPress, traballa cunha función principal chamada "**function __construct()**" a cal lle iremos administrando os datos que precisemos; eses datos serán para insertar datos, modificalos ou borralos, gardar as publicacións, administrador e amosar a informacion en columnas etc... Ao mesmo tempo, o complemento traballará con todos os metadatos que constitúen os campos personalizados que se crean para poder amosalos na pantalla seguindo as condicións que nos lle pidamos; polo que só amosan os datos en función do tipo de publicación ou o valor do campo.**

**A función (function __construct()) constará de outras sub-funcións que se encargan do citado anteriormente e que se amosan na seguinte tabla:**

| add_action( 'init', array( $this, 'register_custom_post_type' ) ); |
| ---------------------------------------- |
| add_action( 'add_meta_boxes', array( $this, 'register_meta_boxes' ) ); |
| add_action( 'save_post', array( $this, 'save_meta_boxes' ) ); |
| add_filter( 'manage_edit-contact_columns', array( $this, 'add_table_columns' ) ); |
| add_action( 'manage_contact_posts_custom_column', array( $this, 'output_table_columns_data'), 10, 2 ); |
| add_filter( 'manage_edit-contact_sortable_columns', array( $this, 'define_sortable_table_columns') ); |
| add_filter( 'request', array( $this, 'orderby_sortable_table_columns' ) ); |
| add_filter( 'posts_join', array ( &$this, 'search_meta_data_join' ) ); |
| add_filter( 'posts_where', array( &$this, 'search_meta_data_where' ) ); |

