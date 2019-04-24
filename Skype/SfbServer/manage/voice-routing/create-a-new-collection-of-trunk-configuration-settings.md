---
title: Criar uma nova coleção de tronco definições de configuração no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços.
ms.openlocfilehash: 86a731c07f3c7289e5eabcd74bb3ccf37ec4df9d
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214719"
---
# <a name="create-a-new-collection-of-trunk-configuration-settings-in-skype-for-business-server"></a>Criar uma nova coleção de tronco definições de configuração no Skype para Business Server

Definições de configuração de tronco SIP definem a relação e os recursos entre um servidor de mediação e o gateway PSTN (rede) telefônica pública comutada, uma troca de filial IP público (PBX) ou um controlador de borda de sessão (SBC) no provedor de serviços. Essas configurações realizam atividades como especificar:
- Se o desvio de mídia deve ser ativado nos troncos.
- As condições nas quais os pacotes RTCP (protocolo) de controle de transporte em tempo real são enviados.
- Ou não a criptografia do protocolo em tempo real seguro (SRTP) é necessário em cada tronco.

Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN).

Ao criar usingSkype de definições de configuração de tronco SIP para o painel de controle do Business Server, as seguintes opções estão disponíveis para você:

|Configuração de UI | Parâmetro do PowerShell | Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. Configuração de mídia for definida usando os cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsMediaConfiguration) e [Set-CsMediaConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsMediaConfiguration) .<br/>Os valores permitidos são:<br/><br/>**Obrigatório**: a criptografia SRTP deve ser usada.<br/>**Opcional**: o SRTP será utilizado se o gateway lhe fornecer apoio.<br/>**Não suportado**: a criptografia SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
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
|Número de chamada|N/D|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número chamado|N/D|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
||||

> [!Note]
> O Skype para Business Server CsTrunkConfiguration cmdlets oferecem suporte a propriedades adicionais não mostradas na Skype para o painel de controle do servidor de negócios. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsTrunkConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsTrunkConfiguration) . 

**Para criar definições de configuração do novo tronco usando Skype para o painel de controle do Business Server**

1. Na Skype para painel de controle do Business Server, clique em **Roteamento de voz**e clique em **Configuração de tronco**.
2. Na guia **Configuração de Tronco**, clique em **Novo** e, em seguida, clique em **Tronco do site** para criar a nova definição no escopo do site, ou **Tronco do pool** para criar as novas definições no escopo do serviço.
3. Em **Selecionar um Site** ou a caixa de diálogo **Selecionar um serviço** (caixa de diálogo que aparece dependem se você estiver criando configurações de escopo de site ou no escopo do serviço), selecione o local para as novas definições de configuração e clique em **Okey **. Se a caixa de diálogo estiver vazia, isso significa que há um local para criar novas configurações; Por exemplo, se a caixa de diálogo **Selecionar um Site** estiver vazia, isso significa que todos os sites já tiverem sido atribuídos uma coleção de sites de configuração de tronco, e cada site (e cada serviço) podem hospedar apenas uma coleção desse tipo. Nesse caso, você pode tanto excluir o conjunto existente e criar um novo conjunto ou simplesmente modificar o conjunto existente.
4. Na caixa de diálogo **Nova configuração de tronco**, faça as seleções apropriadas e clique em **OK**.
5. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
6. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
7. Na caixa de diálogo **Skype para painel de controle de negócios** , clique em **Okey**.
