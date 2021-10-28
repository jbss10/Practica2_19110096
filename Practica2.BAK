
/*
Julian Jhosimar Briano Sanchez.
19110096.
6°E
Sistema Experto.
*/
 :- use_module(library(pce)).
 :- pce_image_directory('./imagenes1').
 :- use_module(library(pce_style_item)).
 :- dynamic color/2.

 resource(img_principal, image, image('img_principal.jpg')).
 resource(portada, image, image('portada.jpg')).

 resource(caso_1, image, image('caso1.jpg')).
 resource(caso_2, image, image('caso2.jpg')).
 resource(caso_3, image, image('caso3.jpg')).
 resource(caso_4, image, image('caso4.jpg')).
 resource(caso_5, image, image('caso5.jpg')).




 resource(escalofrios, image, image('escalofrios_p.jpg')).
 resource(fiebre, image, image('fiebre.jpg')).
 resource(dolor_orina, image, image('dolor_orina.jpg')).
 resource(mal_orina, image, image('mal_orina.jpg')).
 resource(san_orina, image, image('san_orina.jpg')).
 resource(baños_cons, image, image('baños_cons.jpg')).

 resource(costados, image, image('costados.jpg')).
 resource(difi_orin, image, image('difi_orin.jpg')).
 resource(poca_orin, image, image('poca_orin.jpg')).
 resource(san1_orina, image, image('san1_orina.jpg')).
 resource(orin_const, image, image('orin_const.jpg')).
 resource(mail1_orin, image, image('mail1_orin.jpg')).
 resource(dolo_orin, image, image('dolo_orin.jpg')).

 resource(dis_orin, image, image('dis_orin.jpg')).
 resource(falt_air, image, image('falt_air.jpg')).
 resource(debil, image, image('debil.jpg')).
 resource(nauseas, image, image('nauseas.jpg')).
 resource(hincha, image, image('hincha.jpg')).
 resource(dolor_pecho, image, image('dolor_pecho.jpg')).
 resource(rtimo_car, image, image('rtimo_car.jpg')).

 resource(orina_espum, image, image('orina_espum.jpg')).
 resource(hinchazon, image, image('hinchazon.jpg')).
 resource(fatig, image, image('fatig.jpg')).
 resource(aumento_pes, image, image('aumento_pes.jpg')).
 resource(perdida_ape, image, image('perdida_ape.jpg')).

 resource(dolor_espald, image, image('dolor_espald.jpg')).
 resource(perdida_apetito, image, image('perdida_apetito.jpg')).
 resource(fiebre_fuerte, image, image('fiebre_fuerte.jpg')).
 resource(san2_orina, image, image('san2_orina.jpg')).
 resource(peso_perdido, image, image('peso_perdido.jpg')).
 resource(cansancio_frec, image, image('cansancio_frec.jpg')).
 resource(anemia, image, image('anemia.jpg')).





 mostrar_imagen(Pantalla, Imagen) :- new(Figura, figure),
                                     new(Bitmap, bitmap(resource(Imagen),@on)),
                                     send(Bitmap, name, 1),
                                     send(Figura, display, Bitmap),
                                     send(Figura, status, 1),
                                     send(Pantalla, display,Figura,point(0,0)).
  mostrar_imagen_tratamiento(Pantalla, Imagen) :-new(Figura, figure),
                                     new(Bitmap, bitmap(resource(Imagen),@on)),
                                     send(Bitmap, name, 1),
                                     send(Figura, display, Bitmap),
                                     send(Figura, status, 1),
                                     send(Pantalla, display,Figura,point(60,180)).
 nueva_imagen(Ventana, Imagen) :-new(Figura, figure),
                                new(Bitmap, bitmap(resource(Imagen),@on)),
                                send(Bitmap, name, 1),
                                send(Figura, display, Bitmap),
                                send(Figura, status, 1),
                                send(Ventana, display,Figura,point(0,0)).
  imagen_pregunta(Ventana, Imagen) :-new(Figura, figure),
                                new(Bitmap, bitmap(resource(Imagen),@on)),
                                send(Bitmap, name, 1),
                                send(Figura, display, Bitmap),
                                send(Figura, status, 1),
                                send(Ventana, display,Figura,point(500,60)).
  botones:-borrado,
                send(@boton, free),
                send(@btntratamiento,free),
                mostrar_diagnostico(Enfermedad),
                send(@texto, selection('El Diagnostico a partir de los datos obtenidos es:')),
                send(@resp1, selection(Enfermedad)),
                new(@boton, button('Iniciar consulta',
                message(@prolog, botones)
                )),

                new(@btntratamiento,button('Detalles De enfermedad',
                message(@prolog, mostrar_tratamiento,Enfermedad)
                )),
                send(@main, display,@boton,point(20,450)),
                send(@main, display,@btntratamiento,point(138,450)).



  mostrar_tratamiento(X):-new(@tratam, dialog('Tratamiento')),
                          %send(@tratam, append, label(nombre, 'Explicacion: ')),
                          send(@tratam, display,@lblExp1,point(70,5)),
                          send(@tratam, display,@lblExp2,point(50,80)),
                          send(@tratam, display,@r1,point(15,25)),
                          send(@tratam, display,@r2,point(15,40)),
                          send(@tratam, display,@r3,point(15,55)),
                          send(@tratam, display,@r4,point(15,70)),
                          send(@tratam, display,@r5,point(15,85)),
                          send(@tratam, display,@r6,point(15,100)),
                          send(@tratam, display,@r7,point(15,115)),
                          send(@tratam, display,@r8,point(15,130)),
                          send(@tratam, display,@r9,point(15,145)),
                          tratamiento(X),
                          send(@tratam, transient_for, @main),
                          send(@tratam, open_centered).

tratamiento(X):- send(@lblExp1,selection('De Acuerdo Al Diagnostico El Padecimieto Es:')),
                 mostrar_imagen_tratamiento(@tratam,X),
                 tratamientoE(X).

tratamientoE(X):-X == 'caso_1', enf_infeccionesren; X == 'caso_2', enf_piedrasrin; X == 'caso_3', enf_insuren; X == 'caso_4', enf_sinnef; X == 'caso_5', enf_tumren.

enf_infeccionesren:-
send(@r1,selection(' Infeccion en los Riñones:')),
send(@r2, selection('1- Usted presenta un posible cuadro de infección por lo que es recomendable ')),
send(@r3, selection('que acuda a su médico que le corresponde en su clínica más cercana, ya ')),
send(@r4, selection('que si no es tratada puede empeorar y causarle daños en sus riñones.')),
send(@r5, selection('')),
send(@r6, selection('')),
send(@r7, selection('')),
send(@r8, selection('')),
send(@r9, selection('')).

enf_piedrasrin:-
send(@r1,selection('Piedras en los Riñones:')),
send(@r2, selection('2- Las piedras en los riñones son formadas normalmente por altos niveles de ')),
send(@r3, selection('calcio y otros minerales que se encuentran en la orina, por lo que se le ')),
send(@r4, selection('recomienda ir a un médico para que le dé un mejor diagnóstico y un ')),
send(@r5, selection('tratamiento correcto.')),
send(@r6, selection('')),
send(@r7, selection('')),
send(@r8, selection('')),
send(@r9, selection('')).

enf_insuren:-
send(@r1,selection('Insuficiencia renal:')),
send(@r2, selection('3- Usted posiblemente puede tener insuficiencia renal, se le recomienda ir de ')),
send(@r3, selection('carácter urgente con un especialista o algún médico para que le realice un  ')),
send(@r4, selection('diagnóstico preciso y llevar un tratamiento adecuado para evitar mayores ')),
send(@r5, selection('complicaciones.')),
send(@r6, selection('')),
send(@r7, selection('')),
send(@r8, selection('')),
send(@r9, selection('')).

enf_sinnef:-
send(@r1,selection('Síndrome nefrótico:')),
send(@r2, selection('4- Usted probablemente tiene esta enfermedad, se le recomienda ir de ')),
send(@r3, selection('carácter urgente a un médico para que le puedan dar algún tratamiento ')),
send(@r4, selection('oportuno y descartar posibilidades de tener este padecimiento.')),
send(@r5, selection('')),
send(@r6, selection('')),
send(@r7, selection('')),
send(@r8, selection('')),
send(@r9, selection('')).

enf_tumren:-
send(@r1,selection('Tumores renales')),
send(@r2, selection('5- Posiblemente cuenta con esta enfermedad, se le recomienda ir con un ')),
send(@r3, selection('especialista para que le realice un diagnostico preciso y descarte esta ')),
send(@r4, selection('posible enfermedad que es grave')),
send(@r5, selection('')),
send(@r6, selection('')),
send(@r7, selection('')),
send(@r8, selection('')),
send(@r9, selection('')).


   preguntar(Preg,Resp):-new(Di,dialog('Colsultar Datos:')),
                        new(L2,label(texto,'Responde las siguientes preguntas')),
                        id_imagen_preg(Preg,Imagen),
                        imagen_pregunta(Di,Imagen),
                        new(La,label(prob,Preg)),
                        new(B1,button(si,and(message(Di,return,si)))),
                        new(B2,button(no,and(message(Di,return,no)))),
                        send(Di, gap, size(25,25)),
                        send(Di,append(L2)),
                        send(Di,append(La)),
                        send(Di,append(B1)),
                        send(Di,append(B2)),
                        send(Di,default_button,'si'),
                        send(Di,open_centered),get(Di,confirm,Answer),
                        free(Di),
                        Resp=Answer.


  interfaz_principal:-new(@main,dialog('Sistema Experto Diagnostica enfermedades Renales',
        size(1000,1000))),
        new(@texto, label(nombre,'El Diagnostico a partir de los datos es:',font('times','roman',18))),
        new(@resp1, label(nombre,'',font('times','roman',24))),
        new(@lblExp1, label(nombre,'',font('times','roman',14))),
        new(@lblExp2, label(nombre,'',font('times','roman',14))),

        new(@r1, label(nombre,'',font('times','roman',16))),
        new(@r2, label(nombre,'',font('times','roman',14))),
        new(@r3, label(nombre,'',font('times','roman',14))),
        new(@r4, label(nombre,'',font('times','roman',14))),
        new(@r5, label(nombre,'',font('times','roman',14))),
        new(@r6, label(nombre,'',font('times','roman',14))),
        new(@r7, label(nombre,'',font('times','roman',14))),
        new(@r8, label(nombre,'',font('times','roman',14))),
        new(@r9, label(nombre,'',font('times','roman',14))),
        new(@salir,button('SALIR',and(message(@main,destroy),message(@main,free)))),
        new(@boton, button('Iniciar consulta',message(@prolog, botones))),

        new(@btntratamiento,button('Â¿Tratamiento?')),

        nueva_imagen(@main, img_principal),
        send(@main, display,@boton,point(138,450)),
        send(@main, display,@texto,point(60,100)),
        send(@main, display,@salir,point(300,450)),
        send(@main, display,@resp1,point(100,150)),
        send(@main,open_centered).

       borrado:- send(@resp1, selection('')).


interfaz:- new(@interfaz,dialog('Sistema Experto Diagnostica enfermedades renaes',
  size(600,600))),
  new(@titulo, label(nombre,'Bienvenido a Riñon Sano:',font(times, bold, 30))),
  new(@titulo2, label(nombre,'Riñon Seguro:',font(times, bold, 40))),
  new(@info, label(nombre,'Ceti Colomos.',font(scren, italic, 15))),
  new(@info2, label(nombre,'Sistemas Expertos.',font(scren, italic, 15))),
  new(@info3, label(nombre,'Ingenieria en Mecatronica.',font(scren, italic, 15))),
  new(@info4, label(nombre,'Creado Por:',font(scren, italic, 15))),
  new(@info5, label(nombre,'Julian Jhosimar Briano Sanchez.',font(scren, italic, 15))),
  new(@info6, label(nombre,'Registro: 19110096, Grupo: 6°E5.',font(scren, italic, 15))),


  new(BotonComenzar,button('COMENZAR',and(message(@prolog,interfaz_principal) ,
  and(message(@interfaz,destroy),message(@interfaz,free)) ))),
  new(BotonSalir,button('SALIDA',and(message(@interfaz,destroy),message(@interfaz,free)))),

   mostrar_imagen(@interfaz, portada),

  %send(@interfaz,append(BotonComenzar)),
  send(@interfaz, display,BotonComenzar,point(300,550)),
  send(@interfaz, display,BotonSalir,point(400,550)),
  %send(@interfaz,append(BotonSalir)),
  % mostrar_imagen(@interfaz, portada),
  send(@interfaz, display,@titulo,point(10,20)),
  send(@interfaz, display,@titulo2,point(200,60)),
  send(@interfaz, display,@info,point(20,400)),
  send(@interfaz, display,@info2,point(20,420)),
  send(@interfaz, display,@info3,point(20,440)),
  send(@interfaz, display,@info4,point(20,460)),
  send(@interfaz, display,@info5,point(150,465)),
  send(@interfaz, display,@info6,point(150,480)),
  send(@interfaz,open_centered).

  :-interfaz.

 % :-crea_interfaz_inicio.

/* BASE DE CONOCIMIENTOS.
*/

conocimiento('caso_1',
['¿Tiene escalofríos?', '¿Presenta fiebre?',
'¿Tiene sensación de ardor o dolor al orinar?','¿Huele mal cuando va a orinar?','¿Presenta pus o sangre cuando va a orinar?','¿Necesita ir al baño continuamente?']).

conocimiento('caso_2',
['¿Presenta dolor agudo en la espalda, el costado, parte baja del abdomen o ingle?', '¿Tiene dificultades para orinar? ',
'¿Orina en pequeñas cantidades?','¿Presencia de sangre en la orina (color rosado, rojo o café)?','¿Necesidad contante de orinar?','¿Orina mal oliente?','¿Presenta dolor al orinar?']).

conocimiento('caso_3',
['¿Disminuye el volumen de la orina por si sola al ir al baño?',
'¿Siente que le falta el aire?', '¿Presenta debilidad?','¿Tiene nauseas?','¿Presenta hinchazón en las piernas, tobillos o los pies?','¿Presenta dolor en el pecho?','¿Su ritmo cardiaco es regular?']).

conocimiento('caso_4',
['¿Su orina es espumosa?', '¿Presenta hinchazón en ojos, tobillos y pies?',
 '¿Presenta fatiga?','¿Ha aumentado de peso últimamente?','¿Tiene pérdida de apetito?']).

conocimiento('caso_5',
['¿Presenta dolor en la espalda baja?', '¿Ha sufrido de pérdida de apetito?',
 '¿Le ha dado fiebre sin ninguna razón aparente y es difícil de curar?', '¿Presenta sangre al orinar?', '¿Presenta pérdida de peso?', '¿Sufre de cansancio frecuentemente?', '¿Ha presentado cuadros de anemia?']).



id_imagen_preg('¿Tiene escalofríos?','escalofrios').
id_imagen_preg('¿Presenta fiebre?','fiebre').
id_imagen_preg('¿Tiene sensación de ardor o dolor al orinar?','dolor_orina').
id_imagen_preg('¿Huele mal cuando va a orinar?','mal_orina').
id_imagen_preg('¿Presenta pus o sangre cuando va a orinar?','san_orina').
id_imagen_preg('¿Necesita ir al baño continuamente?','baños_cons').

id_imagen_preg('¿Presenta dolor agudo en la espalda, el costado, parte baja del abdomen o ingle?','costados').
id_imagen_preg('¿Tiene dificultades para orinar? ','difi_orin').
id_imagen_preg('¿Orina en pequeñas cantidades?','poca_orin').
id_imagen_preg('¿Presencia de sangre en la orina (color rosado, rojo o café)?','san1_orina').
id_imagen_preg('¿Necesidad contante de orinar?','orin_const').
id_imagen_preg('¿Orina mal oliente?','mail1_orin').
id_imagen_preg('¿Presenta dolor al orinar?','dolo_orin').


id_imagen_preg('¿Disminuye el volumen de la orina por si sola al ir al baño?','dis_orin').
id_imagen_preg('¿Siente que le falta el aire?','falt_air').
id_imagen_preg('¿Presenta debilidad?','debil').
id_imagen_preg('¿Tiene nauseas?','nauseas').
id_imagen_preg('¿Presenta hinchazón en las piernas, tobillos o los pies?','hincha').
id_imagen_preg('¿Presenta dolor en el pecho?','dolor_pecho').
id_imagen_preg('¿Su ritmo cardiaco es regular?','rtimo_car').


id_imagen_preg('¿Su orina es espumosa?','orina_espum').
id_imagen_preg('¿Presenta hinchazón en ojos, tobillos y pies?','hinchazon').
id_imagen_preg('¿Presenta fatiga?','fatig').
id_imagen_preg('¿Ha aumentado de peso últimamente?','aumento_pes').
id_imagen_preg('¿Tiene pérdida de apetito?','perdida_ape').


id_imagen_preg('¿Presenta dolor en la espalda baja?','dolor_espald').
id_imagen_preg('¿Ha sufrido de pérdida de apetito?','perdida_apetito').
id_imagen_preg('¿Le ha dado fiebre sin ninguna razón aparente y es difícil de curar?','fiebre_fuerte').
id_imagen_preg('Presenta sangre al orinar?','san2_orina').
id_imagen_preg('¿Presenta pérdida de peso?','peso_perdido').
id_imagen_preg('¿Sufre de cansancio frecuentemente?','cansancio_frec').
id_imagen_preg('¿Ha presentado cuadros de anemia?','anemia').






 /* MOTOR DE INFERENCIA.
 */
:- dynamic conocido/1.

  mostrar_diagnostico(X):-haz_diagnostico(X),limpiar_ventana.
  mostrar_diagnostico(diagnostico_desconocido):-limpiar_ventana.

  haz_diagnostico(Diagnosis):-
                            obten_hipotesis_y_sintomas(Diagnosis,
                            ListaDeSintomas),
                            prueba_presencia_de(Diagnosis,
                            ListaDeSintomas).


obten_hipotesis_y_sintomas(Diagnosis, ListaDeSintomas):-
                           conocimiento(Diagnosis, ListaDeSintomas).


prueba_presencia_de(Diagnosis, []).
prueba_presencia_de(Diagnosis, [Cabeza | Cola]):-
  prueba_verdad_de(Diagnosis, Cabeza), prueba_presencia_de(Diagnosis, Cola).


prueba_verdad_de(Diagnosis, Sintoma):- conocido(Sintoma).
prueba_verdad_de(Diagnosis, Sintoma):-
 not(conocido(is_false(Sintoma))),
 pregunta_sobre(Diagnosis, Sintoma, Resp), Resp = 'si'.


 pregunta_sobre(Diagnosis, Sintoma, Resp):-
 preguntar(Sintoma,Respuesta),
   process(Diagnosis, Sintoma, Respuesta, Resp).


process(Diagnosis, Sintoma, si, si):- asserta(conocido(Sintoma)).

process(Diagnosis, Sintoma, no, no):- asserta(conocido(is_false(Sintoma))).


limpiar_ventana:- retract(conocido(X)), fail.
limpiar_ventana.


conocido(_):- fail.

not(X):- X,!,fail.
not(_).





