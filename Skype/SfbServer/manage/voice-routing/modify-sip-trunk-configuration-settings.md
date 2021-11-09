---
title: Skype for Business Configurações de tronco SIP serverModify
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 'As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway de rede telefônica pública comutado, um PBX (exchange de filial pública IP) ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. '
ms.openlocfilehash: 0f856c83d6f521308343b626addc0ab2c5e16792
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60829925"
---
# <a name="skype-for-business-servermodify-sip-trunk-configuration-settings"></a>Skype for Business Configurações de tronco SIP serverModify

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:

- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN). Qualquer uma dessas coleções pode ser modificada posteriormente usando o Painel de Controle Skype for Business Server ou Windows PowerShell.

Ao modificar as configurações de tronco SIP usando o Painel de Controle do Servidor Skype for Business Server, as seguintes opções estão disponíveis para você:

|Configuração de UI |Parâmetro do PowerShell |Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando os cmdlets New-CsMediaConfiguration e Set-CsMediaConfiguration de mídia.<br/>Os valores permitidos são:<br/><br/>**Obrigatório:** a criptografia SRTP deve ser usada.<br/>**Opcional**: SRTP será usado se o gateway for compatível com ele.<br/>**Sem suporte:** a criptografia SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
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
|Número chamado|Não disponível|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
|||

> [!Note]
> Os cmdlets Skype for Business Server CsTrunkConfiguration suportam propriedades adicionais não mostradas no Painel de Controle Skype for Business Server. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsTrunkConfiguration.](/powershell/module/skype/Set-CsTrunkConfiguration) 

**Para modificar as configurações do tronco SIP usando o painel de controle Skype for Business Server de controle**

1. No painel Skype for Business Server controle, clique em **Roteamento** de Voz e clique em **Configuração do Tronco.**
2. Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.
3. Na caixa **de diálogo Editar Configuração** do Tronco, faça as seleções apropriadas e clique em **OK**.
4. A propriedade Estado da coleção será atualizada para Não vinculado. Para confirmação das alterações e para excluir a coleção, clique em **Confirmação** e clique em **Comprometer Tudo.**
5. Na caixa **de diálogo Configuração de Voz Não** Confirmado, clique em **OK**.
6. Na caixa **Skype for Business Server Painel de Controle,** clique em **OK**.
