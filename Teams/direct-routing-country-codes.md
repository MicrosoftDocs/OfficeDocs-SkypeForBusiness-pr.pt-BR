---
title: Códigos de país de roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este artigo para localizar os códigos de país do caminho de mídia para Roteamento Direto para que você possa selecionar o caminho de mídia ideal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 69265e797b256186f714e2cd4dcefcb3751c05ee
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904803"
---
# <a name="direct-routing-media-path-country-codes"></a>Códigos de país do caminho de mídia de roteamento direto

Ao escolher um caminho de roteamento para mídia, o Roteamento Direto, por padrão, sempre atribui um datacenter com base no endereço IP público do Controlador de Borda de Sessão (SBC) e sempre seleciona o caminho mais próximo do datacenter SBC.

No entanto, em alguns casos, o caminho de mídia padrão pode não ser o caminho ideal para mídia; por exemplo, um IP público de um intervalo dos Estados Unidos pode ser atribuído a um SBC localizado na Europa. 

Usando o parâmetro -MediaRelayRoutingLocationOverride com os cmdlets New-CsOnlinePSTNGateway e Set-CsOnlinePSTNGateway, você pode especificar a região preferencial para o tráfego de mídia. Por exemplo, o seguinte comando especifica que a região preferencial é a Alemanha:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Observe que a Microsoft só recomenda definir esse parâmetro se os logs de chamada indicarem claramente que a atribuição padrão do datacenter para o caminho de mídia não usa o caminho mais próximo do datacenter SBC. 
 
## <a name="country-code-reference-table"></a>Tabela de referência de código do país

A tabela a seguir mostra os valores de código do país para o parâmetro -MediaRelayRoutingLocationOverride:

| País         | Código 
|-----------------|--------------------|
| Afeganistão     | Af |
| Ilhas Aland   | Machado |
| Albânia         | Al |
| Argélia         | Dz |
| Samoa Americana  | Como |
| Andorra         | AD |
| Angola          | AO |
| Anguila        | IA |
| Antártida      | Aq | 
| Antígua e Barbuda | Ag |
| Argentina       | AR |
| Armênia         | Sou |
| Aruba           | AW |
| Austrália       | AU |
| Áustria         | Em |
| Azerbaijão      | Az |
| Bahamas         | Bs |
| Bahrein         | Bh |
| Bangladesh      | Bd |
| Barbados        | Bb |
| Belarus         | BY |
| Bélgica         | BE |
| Belize          | BZ |
| Benin           | Bj |
| Bermudas         | Bm |
| Butão          | Bt |
| Bolívia         | Bo |
| Bonaire         | Bq |
| Bósnia e Herzegovina | BA |
| Botsuana        | Bw |
| Ilha Bouvet   | Bv |
| Brasil          | BR |
| Território Britânico do Oceano Índico | IO |
| Ilhas Virgens Britânicas | Vg |
| Brunei          | BN |
| Bulgária        | BG |
| Burquina Faso    | Bf |
| Burundi         | Bi |
| Cabo Verde      | Cv |
| Camboja        | Kh |
| Camarões        | Cm |
| Canadá          | CA |
| Ilhas Cayman  | Ky |
| República Centro-Africana | Cf |
| Chad            | Td |
| Chile           | CL |
| China           | CN |
| Ilha de Natal | Cx |
| Ilhas Cocos (Keeling) | Cc |
| Colômbia        | CO |
| Comores         | km |
| Congo           | Cg |
| Congo (RCA)     | Cd |
| Ilhas Cook    | Ck |
| Costa Rica      | Cr |
| Costa do Marfim   | Ci |
| Croácia         | RH |
| Cuba            | CU |
| Curaçao         | Cw |
| Chipre          | CY |
| Chéquia         | Cz |
| Dinamarca         | DK |
| Djibuti        | Dj |
| Dominica        | Dm |
| República Dominicana | DO |
| Equador         | EC |
| Egito           | EG |
| El Salvador     | Sv |
| Guiné Equatorial | Gq |
| Eritreia         | Er |
| Estônia         | EE |
| Eswawawa        | Sz |
| Etiópia        | Et |
| Ilhas Malvinas | Fk |
| Ilhas Faroe   | Fo |
| Fiji            | Fj |
| Finlândia         | FI |
| França          | FR |
| Guiana Francesa   | Gf |
| Polinésia Francesa | Pf |
| Territórios Franceses do Sul | Tf |
| Gabão           | Ga |
| Gâmbia          | Gm |
| Geórgia         | Ge |
| Alemanha         | DE |
| Gana           | Gh |
| Gibraltar       | Gi |
| Grécia          | Gr |
| Groenlândia       | Gl |
| Granada         | Gd |
| Guadalupe      | Gp |
| Guam            | Gu |
| Guatemala       | Gt |
| Guernsey        | Gg |
| Guiné          | Gn |
| Guinea-Bissau   | Gw |
| Guiana          | Gy |
| Haiti           | Oi |
| Ilha Heard e Ilhas McDonald | Hm |
| Honduras        | HN |
| RAE de Hong Kong   | HK |
| Hungria         | HU |
| Islândia         | É |
| Índia           | Em |
| Indonésia       | ID |
| Irã            | IR |
| Iraque            | Qi |
| Irlanda         | IE |
| Ilha de Man     | Mensagem instantânea |
| Israel          | IL |
| Itália           | IT |
| Jamaica         | Jm |
| Jan Mayen       | Xj |
| Japão           | JP |
| Jersey          | Je |
| Jordão          | Jo |
| Cazaquistão      | Kz |
| Quênia           | KE |
| Kiribati        | Ki |
| Coreia           | KR |
| Kosovo          | Xk |
| Kuwait          | Kw |
| Quirguistão      | Kg |
| Laos            | LA |
| Letônia          | Lv |
| Líbano         | Lb |
| Lesoto         | É |
| Libéria         | Lr |
| Líbia           | Ly |
| Liechtenstein   | LI |
| Lituânia       | Tenente |
| Luxemburgo      | LU |
| SAR de Macau       | Mo |
| Madagascar      | Mg |
| Malaui          | Mw |
| Malásia        | MY |
| Maldivas        | Mv |
| Mali            | Ml |
| Malta           | Mt |
| Ilhas Marshall | Mh |
| Martinica      | Mq |
| Mauritânia      | Sr |
| Maurício       | Mu |
| Mayotte         | Yt |
| México          | MX |
| Micronésia      | Fm |
| Moldova         | MD |
| Mônaco          | MC |
| Mongólia        | Mn |
| Montenegro      | Me |
| Montserrat      | Ms |
| Marrocos         | Mãe |
| Moçambique      | Mz |
| Mianmar         | Mm |
| Namíbia         | N/D |
| Nauru           | Nr |
| Nepal           | Np |
| Países Baixos     | NL |
| Nova Caledônia   | NC |
| Nova Zelândia     | Nz |
| Nicarágua       | Ni |
| Níger           | Ne |
| Nigéria         | Ng |
| Niue            | NU |
| Ilha Norfolk  | Nf |
| Coreia do Norte     | Kp |
| Macedônia do Norte | Mk |
| Ilhas Marianas do Norte | Np |
| Noruega          | Não |
| Omã            | Om |
| Paquistão        | Pk |
| Palau           | Pw |
| Autoridade Palestina | Ps |
| Panamá          | PA |
| Nova Guiné | Pg |
| Paraguai        | PY |
| Peru            | PE |
| Filipinas     | PH |
| Ilhas Pitcairn | Pn |
| Polônia          | PL |
| Portugal        | PT |
| Porto Rico     | Pr |
| Catar           | QA |
| Reunião         | Re |
| Romênia         | RO |
| Rússia          | Ru |
| Ruanda          | Rw |
| Saba            | Xs |
| São Cristóvão | Bl |
| São Cristóvão e Névis | Kn |
| Santa Lúcia     | Lc |
| Saint Martin    | Mf |
| São Pedro e Miquelon | Pm |
| São Vicente e Granadinas | VC |
| Samoa           | Ws |
| San Marino      | Sm |
| São Tomé e Principe | St |
| Arábia Saudita    | SA |
| Senegal         | SN |
| Sérvia          | RS |
| Seychelles      | Sc |
| Sierra Leone    | Sl | 
| Singapura       | SG |
| Sint Eustatius  | Xe |
| Sint Maarten    | Sx |
| Eslováquia        | SK |
| Eslovênia        | Sl |
| Ilhas Salomão | Sb |
| Somália         | Então |
| África do Sul    | ZA |
| Ilhas Geórgia do Sul e Sandwich do Sul | Gs |
| Sudão do Sul     | Ss |
| Espanha           | ES |
| Sri Lanka       | Lk |
| Santa Helena, Ascensão, Tristão da Cunha | Sh |
| Sudão           | Sd |
| Suriname        | SR |
| Svalbard        | Sj |
| Suécia          | SE |
| Suíça     | Ch |
| Síria           | Sy |
| Taiwan          | TW |
| Tadjiquistão      | Tj |
| Tanzânia        | Tz |
| Tailândia        | TH |
| Timor-Leste     | Tl |
| Togo            | Tg |
| Tokelau         | Tk |
| Tonga           | Para |
| Trinidad e Tobago | Tt |
| Tunísia         | Tn |
| Turquia          | TR |
| Turcomenistão    | Tm |
| Ilhas Turcos e Caicos | Tc |
| Tuvalu          | Tv |
| Ilhas Distantes dos EUA | UM |
| Ilhas Virgens Americanas | VI |
| Uganda          | Ug |
| Ucrânia         | UA |
| Emirados Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | Nos |
| Uruguai         | UY |
| Uzbequistão      | Uz |
| Vanuatu         | Vu |
| Cidade do Vaticano    | Va |
| Venezuela       | VE |
| Vietnã         | VN |
| Wallis e Futuna | Wf |
| Iêmen           | Vós |
| Zâmbia          | Zm |
| Zimbábue        | Zw |

