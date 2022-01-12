---
title: Planejar Gateway SIP
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
description: Saiba mais sobre o Sip Gateway, como requisitos e benefícios.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4c5f178c5b8da9bf2ed62b06b9c499d676c076e2
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767714"
---
# <a name="plan-for-sip-gateway"></a>Planejar o Gateway SIP

O Gateway SIP permite que sua organização use qualquer dispositivo SIP compatível com Microsoft Teams para preservar seus investimentos em dispositivos SIP. Agora você pode entrar Teams com suas credenciais corporativas e fazer e receber chamadas com um dispositivo SIP compatível. Dispositivos compatíveis podem Skype for Business telefones IP com firmware SIP padrão, telefones IP da Cisco com firmware SIP de várias plataformas ou dispositivos SIP de fornecedores como Poly, Yealink e AudioCodes. Para descobrir como configurar seus dispositivos SIP para Gateway SIP, consulte [Configure SIP Gateway](sip-gateway-configure.md).

## <a name="benefits-of-sip-gateway"></a>Benefícios do Gateway SIP

O Gateway SIP conecta dispositivos SIP compatíveis Teams para ajudar os usuários a migrar perfeitamente para Teams telefonia. Usando o Gateway SIP, os usuários podem fazer o seguinte:

- **Fazer chamadas:** Os usuários do dispositivo SIP podem fazer chamadas para a Rede Telefônica Pública Comutado (PSTN), para outros dispositivos SIP e para Teams e Skype for Business usuários. Os usuários do dispositivo SIP só podem chamar usuários que têm números de telefone.
- **Receber chamadas:** Os usuários de dispositivo SIP podem receber uma chamada da PSTN, de usuários Teams ou Skype for Business que têm dispositivos SIP e de aplicativos cliente Teams e Skype for Business cliente. O dispositivo SIP age como um Teams de extremidade. As chamadas de entrada também serão bifurcadas para o dispositivo SIP do usuário.
- **Várias chamadas simultâneas:** Um usuário de dispositivo SIP em uma chamada pode colocar a chamada em espera para fazer ou receber outras chamadas. Um usuário de dispositivo SIP também pode fazer duas chamadas.
- **Não incomodar:** Um usuário do dispositivo SIP pode definir não incomodar no dispositivo para que o dispositivo não toque para chamadas de entrada. Isso não afeta o status do usuário em todos os outros Teams de extremidade.
- **Hold/Resume e Mute/Unmute:** Um usuário do dispositivo SIP pode segurar e retomar ou silenciar e desativar uma chamada usando os recursos para essas ações no dispositivo.
- **Caixa Postal:** Os usuários do dispositivo SIP podem ouvir mensagens de voz armazenadas eletronicamente que os chamadores deixam para eles.
- **Indicador de espera de mensagem:** Os usuários de dispositivo SIP podem receber notificações que os alertam quando têm novas mensagens de caixa postal.
- **Entrar e sair:** Dispositivos SIP os usuários podem entrar e sair Teams no dispositivo.
- **Multifrequência de tom duplo:** Os usuários do dispositivo SIP podem pressionar teclas de número para fornecer entrada durante chamadas interativas de resposta de voz.
- **Teams reuniões:** um usuário de dispositivo SIP pode ingressar em uma reunião Teams discando o número de acesso à reunião. No momento, não há suporte para discagem para o número de telefone de um usuário da mesma organização. No entanto, os usuários convidados de outra organização podem ser adicionados a uma reunião Teams por um participante que disca para o número de um usuário convidado para incluir esse convidado. **OBSERVAÇÃO:** Adicionar um Teams de reunião por meio de "solicitação de participação" atualmente não alertará um dispositivo SIP.
- **Transferências de chamada:** Os usuários do dispositivo SIP podem transferir chamadas. O Gateway SIP dá suporte a transferências cegas e consultivas.
- **Encaminhamento de chamada local:** Um usuário de dispositivo SIP pode definir regras de encaminhamento (sempre, em tempo de tempo e ocupado) para o dispositivo. Se o dispositivo estiver conectado ao Gateway SIP, a chamada será redirecionada para o endereço de destino com base na regra definida pelo usuário do dispositivo. Para que o encaminhamento de chamada local funcione, o administrador deve definir o `AllowCallRedirect` atributo `Set-CsTeamsCallingPolicy` como `Enabled` . 


## <a name="requirements-to-use-sip-gateway"></a>Requisitos para usar o Gateway SIP

Teams usuários devem ter um número de telefone com chamada PSTN habilitada para usar o Gateway SIP.

### <a name="hardware-software-and-licenses"></a>Hardware, software e licenças

Se você tiver um dispositivo 3PIP ou SIP, deverá ter: 
- Uma licença para Sistema de Telefonia (via E5 ou uma licença autônoma)
- Habilitação PSTN (ou seja, um número de telefone) por meio de um plano de chamada Microsoft Teams, roteamento direto ou Conexão
- Uma licença de Telefone Área Comum para qualquer dispositivo de área comum

## <a name="compatible-devices"></a>Dispositivos compatíveis

|Fornecedor    |Modelo      |Versão mínima do firmware|Versão de firmware aprovada|Comentários|Links|
|----------|-----------|------------|-----------|------------|------------|
|**Cisco** |           |            |           |Os dispositivos que executam o firmware empresarial devem ser convertidos em firmware multiplataforma. Leia o guia à direita para saber como.|[Guia de conversão de firmware da Cisco](https://www.cisco.com/c/en/us/products/collateral/collaboration-endpoints/unified-ip-phone-7800-series/guide-c07-742786.html)|
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
|**Poly**  |           |            |           |O dispositivo reiniciará automaticamente e instalará o firmware selecionado.|   |
|          |VVX150     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX201     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX250     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX300     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX301     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX310     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX311     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX350     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX400     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX401     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX410     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX411     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX450     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX500     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX501     |5.9.5       |6.3.1.8427 |   |   |
|          |VVX600     |5.9.5       |5.9.6.2327 |   |   |
|          |VVX601     |5.9.5       |6.3.1.8427 |   |   |
|**Yealink**|          |            |           |   |[Suporte a yealink](https://support.yealink.com/)|
|          |T40P       |83          |54.84.0.125|   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T41S       |83          |66.85.0.5  |   |   |
|          |T42G       |83          |29.83.0.130|   |   |
|          |T42S       |83          |66.85.0.5  |   |   |
|          |T42U       |83          |108.86.0.20|   |   |
|          |T43U       |83          |108.86.0.20|   |   |
|          |T46S       |83          |66.85.0.5  |   |   |
|          |T46U       |83          |108.86.0.20|   |   |
|          |T48S       |83          |66.85.0.5  |   |   |
|          |T48G       |83          |35.83.0.130|   |   |
|          |T48U       |83          |108.86.0.20|   |   |
|          |T53        |83          |96.85.0.5  |   |   |
|          |T53W       |83          |96.85.0.5  |   |   |
|          |T54W       |83          |96.85.0.5  |   |   |
|          |T57W       |83          |96.85.0.5  |   |   |
|          |T21P       |83          |52.84.0.140|   |   |
|          |T23G       |83          |44.84.0.140|   |   |
|          |T27G       |83          |69.85.0.5  |   |   |
|          |T29G       |83          |46.83.0.130|   |   |
|          |T30        |83          |124.85.0.40|   |   |
|          |T30P       |83          |124.85.0.40|   |   |
|          |T31G       |83          |124.85.0.40|   |   |
|          |T33G       |83          |124.85.0.40|   |   |
|          |T40G       |83          |76.84.0.125|   |   |
|          |T41P       |83          |36.83.0.120|   |   |
|          |T46G       |83          |28.83.0.130|   |   |
|**AudioCodes**|       |            |           |Alguns dispositivos SIP AudioCodes precisam de uma configuração de URL de provisionamento. Baixe e instale arquivos de atualização para os dispositivos AudioCodes afetados à direita. |[Arquivos baixáveis para dispositivos afetados em AudioCodes](https://audiocodes.sharefile.com/share/view/sc9cdf17f9ec45d09/fo19ecda-cf14-4a53-842b-5eab33a0b9b0)|
|          |405         |2.2.8      |2.2.16.525 |   |   |
|          |405HD       |3.2.1      |2.2.16.525 |   |   |
|          |420HD       |3.2.1      |2.2.16.525 |   |   |
|          |430HD       |3.2.1      |2.2.16.525 |   |   |
|          |440HD       |3.2.1      |2.2.16.525 |   |   |
|          |450HD       |3.2.1      |3.4.6.558  |   |   |
|          |C450HD      |3.2.1      |3.4.6.558  |   |   |
|          |445HD       |3.2.1      |3.4.6.558  |   |   |
