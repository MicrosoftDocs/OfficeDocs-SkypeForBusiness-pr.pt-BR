---
title: Planejar o Gateway SIP
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
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Saiba mais sobre o Gateway SIP, como requisitos e benefícios.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: adcaee64e2a95d41229afe580624c6798547cb85
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271696"
---
# <a name="plan-for-sip-gateway"></a>Planejar o Gateway SIP

O Gateway SIP permite que sua organização use qualquer dispositivo SIP compatível com o Microsoft Teams para preservar seus investimentos em dispositivos SIP. Agora você pode entrar no Teams com suas credenciais corporativas e fazer e receber chamadas com um dispositivo SIP compatível. Os dispositivos compatíveis podem ser Skype for Business ip com firmware SIP padrão, telefones IP cisco com firmware SIP multiplataforma ou dispositivos SIP de fornecedores como Poly, Yealink e AudioCodes. Para saber como configurar seus dispositivos SIP para o Gateway SIP, consulte [Configurar o Gateway SIP](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Benefícios do Gateway SIP

O Gateway SIP conecta dispositivos SIP compatíveis ao Teams para ajudar os usuários a migrar diretamente para a telefonia do Teams. Usando o Gateway SIP, os usuários podem fazer o seguinte:

- **Fazer chamadas:** Os usuários do dispositivo SIP podem fazer chamadas para a PSTN (Rede Telefônica Pública Comunada), para outros dispositivos SIP e para o Teams e Skype for Business usuários. Os usuários do dispositivo SIP só podem chamar usuários que têm números de telefone.
- **Receber chamadas:** Os usuários do dispositivo SIP podem receber uma chamada do PSTN, do Teams ou Skype for Business usuários que têm dispositivos SIP e do Teams e Skype for Business aplicativos cliente. O dispositivo SIP atua como um ponto de extremidade do Teams. As chamadas de entrada também serão bifurcadas para o dispositivo SIP do usuário.
- **Várias chamadas simultâneas:** Um usuário do dispositivo SIP em uma chamada pode colocar a chamada em espera para fazer ou receber outras chamadas. Um usuário do dispositivo SIP também pode conferênciar duas chamadas.
- **Não incomodar:** Um usuário do dispositivo SIP pode definir não incomodar no dispositivo para que o dispositivo não toque para chamadas de entrada. Isso não afeta o status do usuário em todos os outros pontos de extremidade do Teams.
- **Espera/Retomada e Mudo/Desativar Mudo:** Um usuário do dispositivo SIP pode manter e retomar ou ativar mudo e desativar o mudo de uma chamada usando os recursos para essas ações no dispositivo.
- **Voicemail:** Os usuários do dispositivo SIP podem escutar mensagens de voz armazenadas eletronicamente que os chamadores deixam para eles.
- **Indicador de espera de mensagem:** Os usuários do dispositivo SIP podem receber notificações que os alertam quando têm novas mensagens de caixa postal.
- **Entrar e sair:** Os usuários de dispositivos SIP podem entrar e sair do Teams no dispositivo.
- **Multi freqüência de tom duplo:** Os usuários do dispositivo SIP podem pressionar teclas de número para fornecer entrada durante chamadas interativas de resposta de voz.
- **Reuniões do Teams:** Um usuário do dispositivo SIP pode ingressar em uma reunião do Teams discando o número de acesso à reunião. Os participantes da reunião podem adicionar um usuário de dispositivo SIP à reunião discando para o número de telefone do usuário ou simplesmente adicionando um participante clicando em 'Solicitar para Ingressar' também alertará o dispositivo SIP do usuário. Os usuários convidados de outra organização podem ser adicionados a uma reunião do Teams por um participante que disca para o número de um usuário convidado para incluir esse convidado.
- **Transferências de chamada:** Os usuários do dispositivo SIP podem transferir chamadas. O Gateway SIP dá suporte a transferências cegas e consultivas.
- **Encaminhamento de chamadas local:** Um usuário do dispositivo SIP pode definir regras de encaminhamento (sempre, no tempo limite e ocupado) para o dispositivo. Se o dispositivo estiver conectado ao Gateway SIP, a chamada será redirecionada para o endereço de destino com base na regra definida pelo usuário do dispositivo. Para fazer com que o encaminhamento de chamadas local funcione, o administrador deve definir o `AllowCallRedirect` atributo como `Set-CsTeamsCallingPolicy` `Enabled`.
- **Dispositivos obsoletos de remoção:** O Gateway SIP dá suporte à remoção automática de dispositivos obsoletos provisionados para um locatário. Dispositivos emparelhados (conectados) serão desativados se não forem conectados por 30 dias e dispositivos não emparelhados (conectados) após 14 dias. Um dispositivo descarregado pode ser integrado novamente após uma redefinição de fábrica.

## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar o Gateway SIP

Os usuários do Teams devem ter um número de telefone com chamada PSTN habilitada para usar o Gateway SIP.

> [!NOTE]
> O Gateway SIP não está disponível para ambientes governamentais (GCC, GCC High e DoD).

### <a name="hardware-software-and-licenses"></a>Hardware, software e licenças

Se você tiver um dispositivo SIP ou 3PIP, deverá ter:

- Uma licença para o Sistema de Telefonia (via E5 ou uma licença autônoma)
- Habilitação de PSTN (ou seja, um número de telefone) por meio de um Plano de Chamada do Microsoft Teams, Roteamento Direto ou Conexão de Operador
- Uma licença do Common Area Phone para qualquer dispositivo de área comum

## <a name="compatible-devices"></a>Dispositivos compatíveis

|Fornecedor    |Modelo      |Versão mínima do firmware|Versão de firmware aprovada|Comentários|Links|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Os dispositivos que executam o firmware corporativo devem ser convertidos em firmware de várias plataformas. Leia o guia à direita para saber como.|[Guia de conversão de firmware da Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
|          |8832       |11.3.5MPP   |11.3.5MPP  |   |   |
|          |6821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7821       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |7861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8811       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8841       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8845       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8851       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8861       |11.1.1MPP   |11-3-3MPP  |   |   |
|          |8865       |11.1.1MPP   |11-3-3MPP  |   |   |
|**Poli**  |           |            |           |O dispositivo reinicializará automaticamente e instalará o firmware selecionado.|   |
|          |Trio 8500  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |Trio 8800  |5.9.5.3182  |7.1.1.0997 |   |   |
|          |VVX150<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601<sup>1</sup>    |5.9.5       |6.3.1.8427 |   |   |
|          |Rove B2    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove B4    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove 30    |8.0.3.0009  |8.0.3.0009 |   |   |
|          |Rove 40    |8.0.3.0009  |8.0.3.0009 |   |   |
|**Yealink**|          |            |           |   |[Suporte a Yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T43U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U<sup>1</sup>      |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T21P_E2    |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T31P       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Alguns dispositivos SIP de AudioCodes precisam de uma configuração de URL de provisionamento. Baixe e instale arquivos de atualização para os dispositivos AudioCodes afetados à direita. |[Arquivos baixáveis para dispositivos afetados em AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo7914a2-4f3a-4000-8957-47bd6f35a3a5)|
|          |405<sup>1</sup>        |2.2.8      |2.2.16.570 |   |   |
|          |405HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |420HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |430HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |440HD<sup>1</sup>      |3.2.1      |2.2.16.570 |   |   |
|          |450HD<sup>1</sup>      |3.2.1      |3.4.6.687  |   |   |
|          |C450HD<sup>1</sup>     |3.2.1      |3.4.6.687  |   |   |
|          |445HD<sup>1</sup>      |3.2.1      |3.4.6.687  |   |   |
|          |RX50<sup>1</sup>       |3.2.1      |3.4.6.687  |   |   |
|**Spectralink**|       |           |           |   |[Suporte a spectralink](https://support.spectralink.com)|
|          |7202        |PCS22B     |PCS22B     |Aparelho |   |
|          |7212        |PCS22B     |PCS22B     |Aparelho |   |
|          |7502        |PCS22B     |PCS22B     |Aparelho |   |
|          |7522        |PCS22B     |PCS22B     |Aparelho |   |
|          |7532        |PCS22B     |PCS22B     |Aparelho |   |
|          |7622        |PCS22B     |PCS22B     |Aparelho |   |
|          |7642        |PCS22B     |PCS22B     |Aparelho |   |
|          |7722        |PCS22B     |PCS22B     |Aparelho |   |
|          |7742        |PCS22B     |PCS22B     |Aparelho |   |
|          |IP-DECT Server 200 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |IP-DECT Server 400 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |IP-DECT Server 6500 |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Virtual IP-DECT Server One |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |
|          |Estação base IP-DECT |PCS22Ab |PCS22Ab |Servidor IP-DECT |   |

<sup>1 O</sup> dispositivo dá suporte à chamada de emergência dinâmica (E911) com o Gateway SIP.

> [!NOTE]
> Os clientes podem usar AudioCodes OVOC e Poly Lens para gerenciar a configuração do lado do dispositivo de seus dispositivos AudioCodes série 400 e Poly VVX/Trio, respectivamente.

> [!NOTE]
> Os handsets spectralink recebem atualizações de firmware pelo ar dos servidores Spectralink IP-DECT.

> [!NOTE]
> Para consultas de suporte, os clientes que usam sistemas IP-DECT com o Gateway SIP do Teams devem entrar em contato com o fabricante de DECT ou seus parceiros de canal de implementação.

> [!NOTE]
> Para alguns dispositivos, a versão mínima do firmware é maior que a versão de firmware aprovada. Isso ocorre porque a versão 3.X é a Skype for Business versão. Atualizamos a versão SIP que é a 2.X.
