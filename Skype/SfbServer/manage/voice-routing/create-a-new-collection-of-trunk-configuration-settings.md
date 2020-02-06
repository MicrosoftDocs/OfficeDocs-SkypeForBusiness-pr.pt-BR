---
title: Criar uma nova coleção de definições de configuração de tronco no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços.
ms.openlocfilehash: 6db4978151bf9b649375adb7a2200710a1a503c3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817001"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Criar uma nova coleção de definições de configuração de tronco no Skype for Business Server

As configurações de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede telefônica pública comutada), um PBX (PBX IP-Public Branch Exchange) ou um SBC (controlador de borda de sessão) no provedor de serviços. Essas configurações realizam atividades como especificar:
- Se o desvio de mídia deve ser ativado nos troncos.
- As condições em que os pacotes de protocolo de controle de transporte em tempo real (RTCP) são enviados.
- Se a criptografia SRTP (Secure Real-Time Protocol) é necessária ou não em cada tronco.

Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).

As opções a seguir estão disponíveis para criar definições de configuração de tronco SIP usingSkype para o painel de controle do Business Server:

|Configuração de UI | Parâmetro do PowerShell | Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) e [set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) .<br/>Os valores permitidos são:<br/><br/>**Obrigatório**: a criptografia do SRTP deve ser usada.<br/>**Opcional**: o SRTP será usado se o gateway oferecer suporte a ele.<br/>**Sem suporte**: a criptografia do SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
|Suporte|Enable3pccRefer<br/>EnableReferSupport|Se definido como **Habilitar envio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.<br/>Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operador conectando a chamada da pessoa A à pessoa B).|
|Habilitar bypass de mídia|EnableBypass|Indica se o bypass de mídia foi habilitado para esse tronco. O bypass de mídia só pode ser habilitado se **Processamento centralizado de mídia** também for habilitado.|
|Processamento centralizado de mídia|ConcentratedTopology|Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)|
|Habilitar RTP com trava|EnableRTPLatching|Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.|
|Habilitar histórico de encaminhamento de chamada|ForwardCallHistory|Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.|
|Habilitar dados de encaminhamento P-Asserted-Identity|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.|
|Habilitar timer de failover do roteamento de saída|EnableFastFailoverTimer|Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.|
|Uso associado de PSTNsages|PSTNUsages|Conjunto de usos PSTN atribuídos ao tronco.|
|Número convertido para testar|Não disponível|Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.|
|Regras de conversão associadas|OutboundTranslationRulesList|Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).|
|Regras de conversão do número chamado|OutboundCallingNumberTranslationRulesList|Conjunto de regras de conversão de número de chamada de saída atribuídas ao tronco.|
|Número de telefone a ser de testado.|Não disponível|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número de chamada|Não disponível|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número chamado|N/D|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
||||

> [!Note]
> Os cmdlets do Skype for Business Server CsTrunkConfiguration dão suporte a propriedades adicionais não mostradas no painel de controle do Skype for Business Server. Para obter mais informações, consulte o tópico da ajuda para o cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**Para criar novas definições de configuração de tronco usando o painel de controle do Skype for Business Server**

1. No painel de controle do Skype for Business Server, clique em **Roteamento de voz**e, em seguida, clique em **configuração de tronco**.
2. Na guia **Configuração de Tronco**, clique em **Novo** e, em seguida, clique em **Tronco do site** para criar a nova definição no escopo do site, ou **Tronco do pool** para criar as novas definições no escopo do serviço.
3. Na caixa de diálogo **selecionar um site** ou **selecionar um serviço** (a caixa de diálogo que aparecerá depende se você está criando configurações de escopo do site ou de escopo do serviço), selecione o local para as novas configurações e clique em **OK**. Se a caixa de diálogo estiver em branco, isso significa que não há lugar para criar as novas configurações; por exemplo, se a caixa de diálogo **selecionar um site** estiver em branco, isso significa que todos os seus sites já foram atribuídos a uma coleção de sites de configuração de tronco, e cada site (e cada serviço) só poderá hospedar uma dessas coleções. Nesse caso, você pode tanto excluir o conjunto existente e criar um novo conjunto ou simplesmente modificar o conjunto existente.
4. Na caixa de diálogo **Nova configuração de tronco**, faça as seleções apropriadas e clique em **OK**.
5. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
6. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
7. Na caixa de diálogo **painel de controle do Skype for Business** , clique em **OK**.
