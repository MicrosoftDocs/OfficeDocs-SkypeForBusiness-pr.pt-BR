---
title: Códigos de país de roteamento direto
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.reviewer: NMuravlyannikov
ms.topic: reference
ms.service: msteams
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Leia este artigo para localizar códigos de país de caminho de mídia para Roteamento Direto para que você possa selecionar o caminho de mídia ideal.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 36124a8aadc94bfd73ffd195ec8ee0a2acf0c2a6
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58582345"
---
# <a name="direct-routing-media-path-country-codes"></a>Códigos de país do caminho de mídia de roteamento direto

Ao escolher um caminho de roteamento para mídia, o Roteamento Direto, por padrão, sempre atribui um datacenter com base no endereço IP público do Controlador de Borda de Sessão (SBC) e sempre seleciona o caminho mais próximo ao datacenter SBC.

No entanto, em alguns casos, o caminho de mídia padrão pode não ser o caminho de mídia ideal; por exemplo, um IP público de um intervalo dos Estados Unidos pode ser atribuído a um SBC localizado na Europa. 

Usando o parâmetro -MediaRelayRoutingLocationOverride com os cmdlets New-CsOnlinePSTNGateway e Set-CsOnlinePSTNGateway, você pode especificar a região preferencial para tráfego de mídia. Por exemplo, o seguinte comando especifica que a região preferencial é a Alemanha:

Set-CSOnlinePSTNGateway -Identity sbc1.contoso.com –MediaRelayRoutingLocationOverride DE 

Observe que a Microsoft só recomenda definir esse parâmetro se os logs de chamada indicarem claramente que a atribuição padrão do datacenter para o caminho de mídia não usa o caminho mais próximo do datacenter SBC. 

> [!NOTE]
> O parâmetro MediaRelayRoutingLocationOverride é reservado para uso com operadoras gerenciadas.
 
## <a name="country-code-reference-table"></a>Tabela de referência de código de país

A tabela a seguir mostra os valores de código do país para o parâmetro -MediaRelayRoutingLocationOverride:

| País         | Código 
|-----------------|--------------------|
| Afeganistão     | AF |
| Ilhas Aland   | AX |
| Albânia         | AL |
| Argélia         | DZ |
| Samoa Americana  | AS |
| Andorra         | AD |
| Angola          | AO |
| Anguila        | AI |
| Antárctida      | AQ | 
| Antígua e Barbuda | AG |
| Argentina       | AR |
| Armênia         | AM |
| Aruba           | AW |
| Austrália       | AU |
| Áustria         | AT |
| Azerbaijão      | AZ |
| Bahamas         | BS |
| Bahrein         | BH |
| Bangladesh      | BD |
| Barbados        | BB |
| Belarus         | BY |
| Bélgica         | BE |
| Belize          | BZ |
| Benin           | BJ |
| Bermudas         | BM |
| Butão          | BT |
| Bolívia         | BO |
| Bonaire         | BQ |
| Bósnia e Herzegovina | BA |
| Botsuana        | BW |
| Ilha Bouvet   | BV |
| Brasil          | BR |
| Território britânico do Oceano Índico | IO |
| Ilhas Virgens Britânicas | VG |
| Brunei          | BN |
| Bulgária        | BG |
| Burquina Faso    | BF |
| Burundi         | BI |
| Cabo Verde      | CV |
| Camboja        | KH |
| Camarões        | CM |
| Canadá          | CA |
| Ilhas Cayman  | KY |
| República Centro-Africana | CF |
| Chade            | TD |
| Chile           | CL |
| China           | CN |
| Ilha Christmas | CX |
| Ilhas Cocos (Quilha) | CC |
| Colômbia        | CO |
| Comores         | KM |
| Congo           | CG |
| Congo (DRC)     | CD |
| Ilhas Cook    | CK |
| Costa Rica      | CR |
| Cote d'Ivoire   | CI |
| Croácia         | RH |
| Cuba            | CU |
| Curaçao         | CW |
| Chipre          | CY |
| Tcheco         | CZ |
| Dinamarca         | DK |
| Djibuti        | DJ |
| Dominica        | DM |
| República Dominicana | DO |
| Equador         | EC |
| Egito           | EG |
| El Salvador     | SV |
| Guiné Equatorial | GQ |
| Eritreia         | ER |
| Estônia         | EE |
| Eswatini        | SZ |
| Etiópia        | ET |
| Ilhas Malvinas | FK |
| Ilhas Faroe   | FO |
| Fiji            | FJ |
| Finlândia         | FI |
| França          | FR |
| Guiana Francesa   | GF |
| Polinésia Francesa | PF |
| Territórios do Sul francês | TF |
| Gabão           | GA |
| Gâmbia          | GM |
| Geórgia         | GE |
| Alemanha         | DE |
| Gana           | GH |
| Gibraltar       | GI |
| Grécia          | GR |
| Groenlândia       | GL |
| Granada         | GD |
| Guadalupe      | GP |
| Guam            | GU |
| Guatemala       | GT |
| Guernsey        | GG |
| Guiné          | GN |
| Guinea-Bissau   | GW |
| Guiana          | GY |
| Haiti           | OI |
| Ilha Heard e Ilhas McDonald | HM |
| Honduras        | HN |
| RAE de Hong Kong   | HK |
| Hungria         | HU |
| Islândia         | IS |
| Índia           | IN |
| Indonésia       | ID |
| Irã            | IR |
| Iraque            | IQ |
| Irlanda         | IE |
| Ilha do Homem     | Mensagem instantânea |
| Israel          | IL |
| Itália           | TI |
| Jamaica         | JM |
| Jan Mayen       | XJ |
| Japão           | JP |
| Jersey          | JE |
| Jordão          | JO |
| Cazaquistão      | KZ |
| Quênia           | KE |
| Kiribati        | KI |
| Coreia           | KR |
| Kosovo          | XK |
| Kuwait          | KW |
| Quirguistão      | KG |
| Laos            | LA |
| Letônia          | LV |
| Líbano         | LB |
| Lesoto         | LS |
| Libéria         | LR |
| Líbia           | LY |
| Liechtenstein   | LI |
| Lituânia       | LT |
| Luxemburgo      | LU |
| SAR de Macau       | MO |
| Madagáscar      | MG |
| Malaui          | MW |
| Malásia        | MY |
| Maldivas        | MV |
| Mali            | ML |
| Malta           | MT |
| Ilhas Marshall | MH |
| Martinica      | MQ |
| Mauritânia      | MR |
| Maurício       | MU |
| Mayotte         | YT |
| México          | MX |
| Micronésia      | FM |
| Moldova         | MD |
| Mônaco          | MC |
| Mongólia        | MN |
| Montenegro      | ME |
| Montserrat      | MS |
| Marrocos         | MA |
| Moçambique      | MZ |
| Mianmar         | MM |
| Namíbia         | N/D |
| Nauru           | NR |
| Nepal           | NP |
| Países Baixos     | NL |
| Nova Caledônia   | NC |
| Nova Zelândia     | NZ |
| Nicarágua       | NI |
| Níger           | NE |
| Nigéria         | NG |
| Niue            | NU |
| Ilha Norfolk  | NF |
| Coreia do Norte     | KP |
| Macedônia do Norte | MK |
| Ilhas Marianas do Norte | NP |
| Noruega          | NÃO |
| Omã            | OM |
| Paquistão        | PK |
| Palau           | PW |
| Autoridade Palestina | PS |
| Panamá          | PA |
| Papua Nova Guiné | PG |
| Paraguai        | PY |
| Peru            | PE |
| Filipinas     | PH |
| Ilhas Pitcairn | PN |
| Polônia          | PL |
| Portugal        | PT |
| Porto Rico     | PR |
| Catar           | QA |
| Reunião         | RE |
| Romênia         | RO |
| Rússia          | RU |
| Ruanda          | RW |
| Saba            | XS |
| Saint Barthélemy | BL |
| São Cristóvão e Névis | KN |
| Santa Lúcia     | LC |
| São Martinho    | MF |
| São Pedro e Miquelon | PM |
| São Vicente e Granadinas | VC |
| Samoa           | WS |
| San Marino      | SM |
| São Tomé e Principe | ST |
| Arábia Saudita    | SA |
| Senegal         | SN |
| Sérvia          | RS |
| Seychelles      | SC |
| Serra Leoa    | SL | 
| Singapura       | SG |
| Sint Eustatius  | XE |
| Sint Maarten    | SX |
| Eslováquia        | SK |
| Eslovênia        | SL |
| Ilhas Salomão | SB |
| Somali         | ENTÃO |
| África do Sul    | ZA |
| Ilhas Geórgia do Sul e Sanduiche do Sul | GS |
| Sudão do Sul     | SS |
| Espanha           | ES |
| Sri Lanka       | LK |
| Santa Helena, Ascensão, Tristão da Cunha | SH |
| Sudão           | SD |
| Suriname        | SR |
| Svalbard        | SJ |
| Suécia          | SE |
| Suíça     | CH |
| Síria           | SY |
| Taiwan          | TW |
| Tadjiquistão      | TJ |
| Tanzânia        | TZ |
| Tailândia        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Tokelau         | TK |
| Tonga           | PARA |
| Trinidad e Tobago | TT |
| Tunísia         | TN |
| Turquia          | TR |
| Turcomenistão    | TM |
| Ilhas Turcos e Caicos | TC |
| Tuvalu          | TV |
| Ilhas U.S. Outlying | UM |
| Ilhas Virgens Americanas | VI |
| Uganda          | UG |
| Ucrânia         | UA |
| Emirados Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | EUA |
| Uruguai         | UY |
| Uzbequistão      | UZ |
| Vanuatu         | VU |
| Cidade do Vaticano    | VA |
| Venezuela       | VE |
| Vietnã         | VN |
| Wallis e Futuna | WF |
| Iêmen           | YE |
| Zâmbia          | ZM |
| Zimbábue        | ZW |
