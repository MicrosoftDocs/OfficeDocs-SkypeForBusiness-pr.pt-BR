---
title: Planejar gateway SIP
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 09/30/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Sip Gateway, como requisitos e benefícios.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5d2bd923835da3c9ffcbf32e0675f1f0e4e63bd3
ms.sourcegitcommit: 0d97dc6616b3d633564409e39c08311af1522705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/14/2022
ms.locfileid: "69392211"
---
# <a name="plan-for-sip-gateway"></a>Planejar o GATEWAY SIP

O Sip Gateway permite que sua organização use qualquer dispositivo SIP compatível com Microsoft Teams para preservar seus investimentos em dispositivos SIP. Agora você pode entrar no Teams com suas credenciais corporativas e fazer e receber chamadas com um dispositivo SIP compatível. Dispositivos compatíveis podem ser Skype for Business telefones IP com firmware SIP padrão, telefones IP Cisco com firmware SIP multiplataforma ou dispositivos SIP de fornecedores como Poly, Yealink e AudioCodes. Para descobrir como configurar seus dispositivos SIP para o SIP Gateway, consulte [Configurar o Gateway SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Benefícios do Gateway SIP

O GATEWAY SIP conecta dispositivos SIP compatíveis ao Teams para ajudar seus usuários a migrar perfeitamente para a telefonia do Teams. Usando o Gateway SIP, seus usuários podem fazer tudo o seguinte:

- **Faça chamadas:** Os usuários do dispositivo SIP podem fazer chamadas para a PSTN (Rede Telefônica Comutada Pública), para outros dispositivos SIP e para usuários do Teams e Skype for Business. Os usuários do dispositivo SIP só podem chamar usuários que têm números de telefone.
- **Receber chamadas:** Os usuários do dispositivo SIP podem receber uma chamada do PSTN, do Teams ou Skype for Business usuários que têm dispositivos SIP e do Teams e Skype for Business aplicativos cliente. O dispositivo SIP atua como um ponto de extremidade do Teams. As chamadas de entrada também serão bifurcadas para o dispositivo SIP do usuário.
- **Várias chamadas simultâneas:** Um usuário de dispositivo SIP em uma chamada pode colocar a chamada em espera para fazer ou receber outras chamadas. Um usuário de dispositivo SIP também pode fazer conferência de duas chamadas.
- **Não perturbe:** Um usuário do dispositivo SIP pode definir não incomodar no dispositivo para que o dispositivo não toque para chamadas de entrada. Isso não tem impacto no status do usuário em todos os outros pontos de extremidade do Teams.
- **Hold/Resume e Mute/Unmute:** Um usuário de dispositivo SIP pode manter e retomar ou silenciar e desmutar uma chamada usando os recursos para essas ações no dispositivo.
- **Voicemail:** Os usuários de dispositivo SIP podem ouvir mensagens de voz armazenadas eletronicamente que os chamadores deixam para eles.
- **Indicador de espera de mensagem:** Os usuários do dispositivo SIP podem receber notificações que os alertam quando têm novas mensagens de caixa postal.
- **Entrada e saída:** Os usuários de dispositivos SIP podem entrar e sair do Teams no dispositivo.
- **Multifrequência de dois tons:** Os usuários do dispositivo SIP podem pressionar chaves numéricas para fornecer entrada durante chamadas interativas de resposta de voz.
- **Reuniões do Teams:** Um usuário do dispositivo SIP pode participar de uma reunião do Teams discando o número de acesso da reunião. Os participantes da reunião podem adicionar um usuário de dispositivo SIP à reunião discando para o número de telefone do usuário ou simplesmente adicionando um participante clicando em 'Solicitar para Ingressar' também alertará o dispositivo SIP do usuário. Usuários convidados de outra organização podem ser adicionados a uma reunião do Teams por um participante que disca para o número de um usuário convidado para incluir esse convidado.
- **Transferências de chamada:** Os usuários do dispositivo SIP podem transferir chamadas. O Gateway SIP dá suporte a transferências cegas e consultivas.
- **Encaminhamento de chamada local:** Um usuário do dispositivo SIP pode definir regras de encaminhamento (sempre, em tempo limite e ocupado) para o dispositivo. Se o dispositivo estiver conectado ao Gateway SIP, a chamada será redirecionada para o endereço de destino com base na regra definida pelo usuário do dispositivo. Para fazer o encaminhamento de chamadas local funcionar, o administrador deve definir o `AllowCallRedirect` atributo como `Set-CsTeamsCallingPolicy` `Enabled`.
- **Dispositivos obsoletos de offboard:** O GATEWAY SIP dá suporte ao offboard automático de dispositivos obsoletos provisionados para um locatário. Os dispositivos emparelhados (conectados) serão desligados se não estiverem conectados por 30 dias e dispositivos não conectados (de saída) após 14 dias. Um dispositivo offboarded pode ser re-integrado após uma redefinição de fábrica.

## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar o GATEWAY SIP

Os usuários do Teams devem ter um número de telefone com chamadas PSTN habilitadas para usar o Gateway SIP.

> [!NOTE]
> O Gateway SIP não está disponível para ambientes governamentais (GCC, GCC High e DoD).

### <a name="hardware-software-and-licenses"></a>Hardware, software e licenças

Se você tiver um dispositivo 3PIP ou SIP, deverá ter:

- Uma licença para Microsoft Teams, Skype for Business Plano Online 2 e Microsoft sistema telefônico 365 (via E5 ou licenças autônomas)
- Habilitação PSTN (ou seja, um número de telefone) por meio de um Microsoft Plano de Chamada do Teams, Roteamento Direto ou Conexão de Operador
- Uma **licença Microsoft dispositivos compartilhados do Teams** para qualquer dispositivo de área comum

## <a name="compatible-devices"></a>Dispositivos compatíveis

|Fornecedor    |Modelo      |Versão mínima do firmware|Versão de firmware aprovada|Comentários|Links|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Os dispositivos que executam firmware corporativo devem ser convertidos em firmware multiplataforma. Leia o guia à direita para saber como.|[Guia de conversão de firmware da Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832<sup>1</sup>       |11.3.5MPP   |11-3-7MPP  |   |   |
|          |6821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7821<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |7861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8811<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8841<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8845<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8851<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8861<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|          |8865<sup>1</sup>       |11.1.1MPP   |11-3-7MPP  |   |   |
|**Poli**  |           |            |           |O dispositivo reiniciará automaticamente e instalará o firmware selecionado.|   |
|          |Trio 8500  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.2.2.1094 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.7.3480 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove B4    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 30    |8.0.3.0010  |8.0.3.0010 |   |   |
|          |Rove 40    |8.0.3.0010  |8.0.3.0010 |   |   |
|**Yealink**|          |            |           |   |[Suporte ao Yealink](https://support.yealink.com/)|
|          |T21P       |83          |34.72.0.75 |   |   |
|          |T21P_E2    |83          |52.84.0.125|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G<sup>1</sup>      |83          |69.86.0.15 |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30<sup>1</sup>       |83          |124.86.0.40|   |   |
|          |T30P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T31P<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T33G<sup>1</sup>      |83          |124.86.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T41S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T43U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|          |T46S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48S<sup>1</sup>      |83          |66.86.5.1  |   |   |
|          |T48U<sup>1</sup>      |83          |108.86.5.1 |   |   |
|          |T53<sup>1</sup>       |83          |96.86.5.1  |   |   |
|          |T53W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T54W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |T57W<sup>1</sup>      |83          |96.86.5.1  |   |   |
|          |W56H                  |            |61.85.0.56 |   |   |
|          |W73H                  |            |116.85.0.38|   |   |
|          |W59R                  |            |115.85.0.56|   |   |
|          |W70B NOAM             |            |146.85.5.4 |   |   |
|          |W70B EMEA             |            |146.85.5.2 |   |   |
|          |W70B APAC             |            |146.85.5.3 |   |   |
|          |W80 NOAM              |            |130.85.5.5 |   |   |
|          |W80 EMEA              |            |130.85.5.6 |   |   |
|          |W80 APAC              |            |130.85.5.4 |   |   |
|          |W90 NOAM              |            |130.85.5.5 |   |   |
|          |W90 EMEA              |            |130.85.5.6 |   |   |
|          |W90 APAC              |            |130.85.5.4 |   |   |
|**AudioCodes**|       |            |           |Alguns dispositivos SIP de AudioCodes precisam de uma configuração de URL de provisionamento. Baixe e instale arquivos de atualização para os dispositivos AudioCodes afetados à direita. |[Arquivos baixáveis para dispositivos afetados em AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.589 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |405HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |420HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |430HDG<sup>1</sup>     |3.2.1      |2.2.16.589 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.589 |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704 |   |   |
|          |445HDG<sup>1</sup>     |3.2.1      |3.4.6.704 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.704  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.704  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.704  |   |   |
|**Spectralink**|       |           |           |   |[Suporte ao Spectralink](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |Aparelho |   |
|          |7212        |PCS22B     |PCS22B     |Aparelho |   |
|          |7502        |PCS22B     |PCS22B     |Aparelho |   |
|          |7522        |PCS22B     |PCS22B     |Aparelho |   |
|          |7532        |PCS22B     |PCS22B     |Aparelho |   |
|          |7622        |PCS22B     |PCS22B     |Aparelho |   |
|          |7642        |PCS22B     |PCS22B     |Aparelho |   |
|          |7722        |PCS22B     |PCS22B     |Aparelho |   |
|          |7742        |PCS22B     |PCS22B     |Aparelho |   |
|          |Servidor IP-DECT 200 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Servidor IP-DECT 400 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Servidor IP-DECT 6500 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Servidor IP-DECT Virtual One |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Estação Base IP-DECT |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|**Ascom**|       |           |           |   |[Suporte do Ascom](https://www.ascom.com/products-and-services/services/support-and-maintenance/)|
|          |Ascom d43        |2.11.4     |2.11.4     |Aparelho |   |
|          |Ascom d63        |2.11.4     |2.11.4     |Aparelho |   |
|          |Ascom d81        |4.13.1     |4.13.1     |Aparelho |   |
|          |Ascom d83        |4.13.1     |4.13.1     |Aparelho |   |
|          |Ascom Myco 3 DECT        |3.4.1     |3.4.1     |Aparelho |   |
|          |IPBSx do Ponto de Acesso IP-DECT        |11.8.8     |11.8.8     |Ponto de acesso IP-DECT |   |
|          |IP-DECT Gateway IPBL     |11.8.8     |11.8.8     |IP-DECT Gateway |   |
|          |Estação Base TDM        |R3N     |R3N     |Estação Base IP-DECT |   |
|          |IP-DECT Virtual Appliance IPVM        |11.8.8     |11.8.8     |Servidor IP-DECT |   |

<sup>1</sup> O dispositivo dá suporte à chamada de emergência dinâmica (E911) com o Gateway SIP.

> [!NOTE]
> Os clientes podem usar os AudioCodes OVOC e Poly Lens para gerenciar a configuração do lado do dispositivo de seus dispositivos AudioCodes 400 e Poly VVX/Trio, respectivamente.

> [!NOTE]
> Os aparelhos Spectralink recebem atualizações de firmware no ar de servidores IP-DECT do Spectralink.

> [!NOTE]
> Os aparelhos Ascom recebem atualizações de firmware no ar de servidores AScom IP-DECT.

> [!NOTE]
> Para Estações Base de DECT do Yealink, use a versão de firmware específica da região apropriada listada acima para ter a melhor experiência de chamada.

> [!NOTE]
> Para consultas de suporte, os clientes que usam sistemas IP-DECT com o Teams SIP Gateway devem entrar em contato com seu fabricante de DECT ou seus parceiros de canal de implementação.

> [!NOTE]
> Para alguns dispositivos, a versão de firmware mínimo é maior que a versão de firmware aprovada. Isso ocorre porque a versão 3.X é a versão Skype for Business. Atualizamos a versão SIP que é 2.X.
