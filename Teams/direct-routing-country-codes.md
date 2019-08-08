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
ms.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
description: Leia este artigo para localizar códigos de país do caminho de mídia para roteamento direto.
ms.openlocfilehash: 5956f538df5aefc356e960f8eb2817602ef99884
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36237452"
---
# <a name="direct-routing-media-path-country-codes"></a>Código de caminho de mídia de roteamento direto

Ao escolher um caminho de roteamento para mídia, o roteamento direto, por padrão, sempre atribui um datacenter com base no endereço IP público do controlador de borda de sessão (SBC) e sempre seleciona o caminho mais próximo ao Datacenter do SBC.

No entanto, em alguns casos o caminho de mídia padrão pode não ser o caminho de mídia ideal; por exemplo, um IP público de uma faixa de Estados Unidos pode ser atribuído a um SBC localizado na Europa. 

Usando o parâmetro-MediaRelayRoutingLocationOverride com os cmdlets New-CsOnlinePSTNGateway e Set-CsOnlinePSTNGateway, você pode especificar a região preferida para o tráfego de mídia. Por exemplo, o comando a seguir especifica que a região preferida é a Alemanha:

Set-CSOnlinePSTNGateway-Identity sbc1.contoso.com – MediaRelayRoutingLocationOverride DE 

Observe que a Microsoft recomenda a configuração desse parâmetro apenas se os logs de chamada indicar claramente que a atribuição padrão do datacenter para o caminho de mídia não use o caminho mais próximo ao Datacenter do SBC. 
 
## <a name="country-code-reference-table"></a>Tabela de referência de código de país

A tabela a seguir mostra os valores de código de país para o parâmetro-MediaRelayRoutingLocationOverride:

| País         | Codinome 
|-----------------|--------------------|
| Afeganistão     | AF |
| Ilhas Aland   | Dynamics |
| Albânia         | AL |
| Argélia         | DZ |
| Samoa Americana  | COMO |
| Andorra         | AD |
| Angola          | AO |
| Anguilla        | AL |
| Horário      | CAPTURA | 
| Antígua e Barbuda | AG |
| Argentina       | AR |
| Armênia         | ME |
| Aruba           | AW |
| Austrália       | AU |
| Áustria         | COMO |
| Azerbaijão      | RJ |
| Bahamas         | BS |
| Bahrein         | BH |
| Bangladesh      | BD |
| Barbados        | CONSTRUÇÃO |
| Belarus         | BY |
| Bélgica         | BE |
| Belize          | BZ |
| Benin           | TROCAR |
| Bermuda         | BM |
| Butão          | BT |
| Bolívia         | BO |
| Bonaire         | BQ até |
| Bosnia and Herzegovina (Bosna i Hercegovina) | BA |
| Botsuana        | LARGURA |
| Ilha Bouvet   | BV |
| Brasil          | BR |
| Território britânico do Oceano Índico | / |
| Ilhas Virgens Britânicas | VG |
| Brunei          | BN |
| Bulgária        | BG |
| Burkina Faso    | BF |
| Burundi         | DOBRA |
| Cabo verde      | INICIA |
| Camboja        | KH |
| Camarões        | CM |
| Canadá          | CA |
| Ilhas Cayman  | KY |
| República Centro-Africana | TC |
| Chad            | TD |
| Chile           | CL |
| China           | CN |
| Ilha Christmas | CX |
| Ilhas Cocos (Keeling) | CP |
| Colômbia        | CO |
| Ilhas Comores         | km |
| Congo           | CG |
| Congo (RDC)     | CD |
| Ilhas Cook    | CK |
| Costa Rica      | ² |
| Costa d' Ivoire   | CI |
| Croácia         | RH |
| Cuba            | RECOR |
| Curaçau         | PV |
| Chipre          | CY |
| Czechia         | CZ |
| Dinamarca         | DK |
| Djibuti        | DJ |
| Dominica        | MINERAÇÃO |
| República Dominicana | FAZER |
| Equador         | EC |
| Egito           | EG |
| El Salvador     | VA |
| Guiné Equatorial | GQ |
| Eritreia         | ER |
| Estônia         | EE |
| Eswatini        | St |
| Etiópia        | ET |
| Ilhas Malvinas | CE |
| Ilhas Faroés   | HETEROGÊNEO |
| Ilhas            | FJ |
| Finlândia         | FI |
| França          | FR |
| Guiana francesa   | GF |
| Polinésia francesa | REPETIÇÃO |
| Territórios franceses do Sul | TF |
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
| Guiné-Bissau   | GW |
| Guiana          | GY |
| Haiti           | Oi |
| Ilha Heard e Ilhas McDonald | HM |
| Honduras        | HN |
| Hong Kong SAR   | HK |
| Hungria         | HU |
| Islândia         | CONSISTE |
| Índia           | NO |
| Indonésia       | ID |
| Irã            | RI |
| Iraque            | IQ |
| Irlanda         | IE |
| Ilha de Man     | Mensagem instantânea |
| Israel          | IL |
| Itália           | RECOMENDA |
| Jamaica         | JM |
| Jan Mayen       | XJ |
| Japão           | JP |
| Jersey          | JE |
| Jordânia          | Joana |
| Cazaquistão      | KZ |
| Quênia           | KE |
| Kiribati        | KI |
| Coreia           | KR |
| Kosovo          | XK |
| Kuaite          | KW |
| Quirguistão      | KG |
| Laos            | LA |
| Letônia          | LV |
| Líbano         | LB |
| Lesoto         | LS |
| Libéria         | LR |
| Líbia           | LY |
| Liechtenstein   | LI |
| Lituânia       | PRAZO |
| Luxemburgo      | LU |
| Rae de Macau       | MO |
| Madagascar      | MG |
| Malaui          | MW |
| Malásia        | MY |
| Maldivas        | MV |
| Mali            | ML |
| Malta           | MT |
| Ilhas Marshall | MH |
| Martinica      | MQ |
| Mauritânia      | MR |
| Ilhas       | MEU |
| Mayotte         | YT |
| México          | MX |
| Micronésia      | FM |
| Moldova         | MD |
| Mônaco          | MC |
| Mongólia        | MN |
| Montenegro      | -ME |
| Montserrat      | Srta |
| Marrocos         | MA |
| Moçambique      | MZ |
| Sinal         | CM |
| Namíbia         | N/D |
| Nauru           | N º cheque |
| Nepal           | NP |
| Países Baixos     | NL |
| Nova Caledônia   | NC |
| Nova Zelândia     | NZ |
| Nicarágua       | NI |
| Níger           | NE |
| Nigéria         | ÇÃO |
| Niue            | NU |
| Ilha Norfolk  | NF |
| Coreia do Norte     | KP |
| Nordeste da Macedônia | PODERÃO |
| Ilhas Marianas do Norte | NP |
| Noruega          | Não |
| Omã            | OM |
| Paquistão         | CP |
| Palau           | SENHA |
| Autoridade Palestina | PROFISSIONAIS |
| Panamá          | PA |
| Papua Nova Guiné | PÁG |
| Paraguai        | PY |
| Peru            | PE |
| Filipinas     | PH |
| Ilhas Pitcairn | NP |
| Polônia          | PL |
| Portugal        | PT |
| Porto Rico     | R |
| Catar           | QA |
| Reuniões         | NOVAMENTE |
| Romênia         | RO |
| Rússia          | RU |
| Ruanda          | RWs |
| Saba            | XS |
| São Barthelemy | BL |
| São Cristóvão e Névis | KN |
| Santa Lúcia     | LC |
| São Martins    | MF |
| São Pedro e Miquelon | 23:00 |
| São Vicente e Granadinas | VOZ |
| Ocidental           | WS |
| San Marino      | SM |
| São Tomé e Príncipe | PRAZO |
| Saudi Arabia (المملكة العربية السعودية)    | SA |
| Senegal         | SN |
| Sérvia          | RS |
| Seychelles      | SC |
| Serra Leoa    | SL | 
| Cingapura       | SG |
| Santo Eustáquio  | ÍNDICE |
| Santo Maarten    | MÉTODO SX |
| Eslováquia        | SK |
| Eslovênia        | SL |
| Ilhas Salomão | SB |
| Somália         | Então |
| África do Sul    | ZA |
| Ilhas Geórgia do Sul e Sandwich do Sul | GS |
| Sudão do Sul     | SS |
| Espanha           | ES |
| Sri Lanka       | LK |
| Santa Helena, ascensão e Tristão da Cunha | & |
| Sudão           | SD |
| Suriname        | RESTAURO |
| Ilhas        | SJ |
| Suécia          | SE |
| Suíça     | CH |
| Síria           | SY |
| Taiwan          | TW |
| Tadjiquistão      | TJ |
| Tanzânia        | TZ |
| Tailândia        | TH |
| Timor-Leste     | TL |
| Togo            | TG |
| Toquelau         | TK |
| Tonga           | Para |
| Trinidad e Tobago | TT |
| Tunísia         | TN |
| Turquia          | TR |
| Turcomenistão    | ™ |
| Ilhas Turks e Caicos | TC |
| Tuvalu          | PROGRAMA |
| Territórios insulares dos EUA | Hmm |
| Ilhas Virgens americanas | VI |
| Xelim          | UG |
| Ucrânia         | ASSISTÊNCIA |
| Emirados Árabes Unidos | AE |
| Reino Unido  | GB |
| Estados Unidos   | Junte |
| Uruguai         | UY |
| Uzbequistão      | UZ |
| Vanuatu         | VU |
| Cidade do Vaticano    | VA |
| Venezuela       | VE |
| Vietnã         | VN |
| Ilhas Wallis e Futuna | WCF |
| Iêmen           | YE |
| Zâmbia          | ZM |
| Zimbábue        | ZW |

