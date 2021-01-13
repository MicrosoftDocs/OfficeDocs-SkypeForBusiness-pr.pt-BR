---
title: Modificar as definições de configuração do tronco SIP no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. '
ms.openlocfilehash: a4c91d447fd61a2763fcabce492e4f85f88cb538
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827721"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar as definições de configuração do tronco SIP no Skype for Business Server

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala o Skype for Business Server, um conjunto global de definições de configuração de tronco SIP é criado para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Qualquer uma dessas coleções pode ser modificada posteriormente usando o Painel de Controle do Skype for Business Server ou o Windows PowerShell.

Ao modificar as definições de configuração do tronco SIP usando o Painel de Controle do Skype for Business Server Server, as seguintes opções estão disponíveis:

|Configuração de UI |Parâmetro do PowerShell |Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando os cmdlets New-CsMediaConfiguration e Set-CsMediaConfiguration mídia.<br/>Os valores permitidos são:<br/><br/>**Obrigatório:** a criptografia SRTP deve ser usada.<br/>**Opcional:** o SRTP será usado se o gateway oferece suporte a ele.<br/>**Sem Suporte:** a criptografia SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
|Suporte|Enable3pccRefer<br/>EnableReferSupport|Se definido como **Habilitar endio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.<br/>Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operados conectando a chamada da pessoa A à pessoa B).|
|Habilitar bypass de mídia|EnableBypass|Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.|
|Processamento centralizado de mídia|ConcentratedTopology|Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)|
|Habilitar RTP com trava|EnableRTPLatching|Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.|
|Habilitar histórico de encaminhamento de chamada|ForwardCallHistory|Indica se as informações de histórico de chamada serão encaminhadas pelo tronco.|
|Habilitar dados de encaminhamento P-Asserted-Identity|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.|
|Habilitar timer de failover do roteamento de saída|EnableFastFailoverTimer|Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.|
|Uso associado de PSTNsages|PSTNUsages|Coleção de usos de PSTN atribuídos ao tronco.|
|Número convertido para testar|N/D|Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.|
|Regras de conversão associadas|OutboundTranslationRulesList|Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).|
|Regras de conversão do número chamado|OutboundCallingNumberTranslationRulesList|Coleção de regras de conversão do número de chamada de saída atribuído ao tronco.|
|Número de telefone a ser de testado.|N/D|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número de chamada|N/D|Indica que o número de telefone a ser testado é o número do chamador.|
|Número chamado|N/D|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
|||

> [!Note]
> Os cmdlets CsTrunkConfiguration do Skype for Business Server suportam propriedades adicionais não mostradas no Painel de Controle do Skype for Business Server. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsTrunkConfiguration.](https://docs.microsoft.com/powershell/module/skype/Set-CsTrunkConfiguration) 

**Para modificar as definições de configuração do tronco SIP usando o Painel de Controle do Skype for Business Server**

1. No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e em **Configuração de Tronco.**
2. Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.
3. Na caixa **de diálogo Editar Configuração** de Tronco, faça as seleções apropriadas e clique em **OK.**
4. A propriedade Estado da coleção será atualizada para Não vinculado. Para comprometer as alterações e excluir a coleção, clique em **Commit** e em **Commit All**.
5. Na caixa **de diálogo Definição de Configuração de Voz** Não Confirmado, clique em **OK.**
6. Na caixa de diálogo Painel de **Controle do Skype for Business Server,** clique em **OK.**
