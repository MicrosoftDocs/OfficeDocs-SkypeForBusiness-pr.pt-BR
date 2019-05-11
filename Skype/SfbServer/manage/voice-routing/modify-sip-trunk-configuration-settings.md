---
title: Modificar as definições de configuração de tronco SIP no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. '
ms.openlocfilehash: 0224a0e22aa12c5efa0c04d2eae568618954afc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920443"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar as definições de configuração de tronco SIP no Skype para Business Server

Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. Essas configurações realizam atividades como especificar:

- Se o desvio de mídia deve ser ativado nos troncos.
- As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.
- Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.

Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN). Qualquer uma dessas coleções podem serem modificada posteriormente usando qualquer um do Skype para painel de controle do Business Server ou o Windows PowerShell.

Ao modificar as definições de configuração de tronco SIP usando o Skype para painel de controle de servidor do Business Server, as seguintes opções estão disponíveis para você:

|Configuração de UI |Parâmetro do PowerShell |Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. Configuração de mídia for definida usando os cmdlets New-CsMediaConfiguration e Set-CsMediaConfiguration.<br/>Os valores permitidos são:<br/><br/>**Obrigatório**: a criptografia SRTP deve ser usada.<br/>**Opcional**: o SRTP será utilizado se o gateway lhe fornecer apoio.<br/>**Não suportado**: a criptografia SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
|Suporte|Enable3pccRefer<br/>EnableReferSupport|Se definido como **Habilitar envio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.<br/>Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operador conectando a chamada da pessoa A à pessoa B).|
|Habilitar bypass de mídia|EnableBypass|Indica se o bypass de mídia foi habilitado para esse tronco. O bypass de mídia só pode ser habilitado se **Processamento centralizado de mídia** também for habilitado.|
|Processamento centralizado de mídia|ConcentratedTopology|Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)|
|Habilitar RTP com trava|EnableRTPLatching|Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.|
|Habilitar histórico de encaminhamento de chamada|ForwardCallHistory|Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.|
|Habilitar dados de encaminhamento P-Asserted-Identity|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.|
|Habilitar timer de failover do roteamento de saída|EnableFastFailoverTimer|Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.|
|Uso associado de PSTNsages|PSTNUsages|Conjunto de usos PSTN atribuídos ao tronco.|
|Número convertido para testar|N/D|Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.|
|Regras de conversão associadas|OutboundTranslationRulesList|Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).|
|Regras de conversão do número chamado|OutboundCallingNumberTranslationRulesList|Conjunto de regras de conversão de número de chamada de saída atribuídas ao tronco.|
|Número de telefone a ser de testado.|N/D|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número de chamada|N/D|Indica que o número de telefone a ser testado é o número do chamador.|
|Número chamado|N/D|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
|||

> [!Note]
> O Skype para Business Server CsTrunkConfiguration cmdlets oferecem suporte a propriedades adicionais não mostradas no Skype para o painel de controle do servidor de negócios. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsTrunkConfiguration) . 

**Para modificar as definições de configuração de tronco SIP usando o Skype para o painel de controle do Business Server**

1. Na Skype para painel de controle do Business Server, clique em **Roteamento de voz**e clique em **Configuração de tronco**.
2. Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.
3. Na caixa de diálogo **Editar configuração do tronco** , faça as seleções apropriadas e clique em **Okey**.
4. A propriedade Estado da coleção será atualizada para Não vinculado. Para confirmar as alterações e exclua o conjunto, clique em **Confirmar**e, em seguida, clique em **Confirmar tudo**.
5. Na caixa de diálogo **Definição de configuração de voz não confirmadas**, clique em **Okey**.
6. Na caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.
