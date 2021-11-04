---
title: 'Skype for Business Server: criar uma nova coleção de configurações de tronco'
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: As configurações de tronco SIP definem a relação entre um Servidor de Mediação e o gateway PSTN (rede telefônica pública comutado), um PBX (exchange de filial pública IP) ou um Controlador de Borda de Sessão (SBC) no provedor de serviços.
ms.openlocfilehash: 863123c21db831146a03de946992a1eb7ed06840
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763549"
---
# <a name="skype-for-business-server-create-a-new-collection-of-trunk-configuration-settings"></a>Skype for Business Server: criar uma nova coleção de configurações de tronco

As definições de configuração de tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e gateway PSTN, um PBX-IP ou um SBC no provedor de serviços. Estas configurações fazem coisas como especificar:
- Se o bypass de mídia deve ser habilitado nos troncos.
- As condições nas quais os pacotes RTCP são enviados.
- Se a criptografia SRTP é obrigatória em cada tronco.

Quando você instala Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).

Ao criar configurações de tronco SIP usando o Painel de Controle do Servidor De Negócios DoSkype para Empresas, as seguintes opções estão disponíveis para você:

|Configuração de UI | Parâmetro do PowerShell | Descrição |
|--|--|--|
|Nome|Identidade|Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.|
|Descrição|Descrição|Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).|
|Máximo de diálogos iniciais suportados|MaxEarlyDialogs|O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.|
|Nível de suporte de criptografia|SRTPMode|Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando os cmdlets [New-CsMediaConfiguration](/powershell/module/skype/New-CsMediaConfiguration) e [Set-CsMediaConfiguration.](/powershell/module/skype/Set-CsMediaConfiguration)<br/>Os valores permitidos são:<br/><br/>**Obrigatório:** a criptografia SRTP deve ser usada.<br/>**Opcional**: SRTP será usado se o gateway for compatível com ele.<br/>**Sem suporte:** a criptografia SRTP não é suportada e, portanto, não será usada.<br/><br/>SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.|
|Suporte|Enable3pccRefer<br/>EnableReferSupport|Se definido como **Habilitar endio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.<br/>Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operados conectando a chamada da pessoa A à pessoa B).|
|Habilitar bypass de mídia|EnableBypass|Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.|
|Processamento centralizado de mídia|ConcentratedTopology|Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)|
|Habilitar RTP com trava|EnableRTPLatching|Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.|
|Habilitar histórico de encaminhamento de chamada|ForwardCallHistory|Indica se as informações de histórico de chamada serão encaminhadas pelo tronco.|
|Habilitar dados de encaminhamento P-Asserted-Identity|ForwardPAI|Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.|
|Habilitar timer de failover do roteamento de saída|EnableFastFailoverTimer|Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.|
|Uso associado de PSTNsages|PSTNUsages|Coleção de usos de PSTN atribuídos ao tronco.|
|Número convertido para testar|N/A|Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.|
|Regras de conversão associadas|OutboundTranslationRulesList|Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).|
|Regras de conversão do número chamado|OutboundCallingNumberTranslationRulesList|Coleção de regras de conversão do número de chamada de saída atribuído ao tronco.|
|Número de telefone a ser de testado.|N/A|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número de chamada|N/A|Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.|
|Número chamado|N/A|Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.|
||||

> [!Note]
> Os cmdlets Skype for Business Server CsTrunkConfiguration suportam propriedades adicionais não mostradas Skype for Business Server Painel de Controle. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsTrunkConfiguration.](/powershell/module/skype/New-CsTrunkConfiguration) 

**Para criar novas configurações de tronco usando Skype for Business Server Painel de Controle**

1. No painel Skype for Business Server controle, clique em **Roteamento** de Voz e clique em **Configuração do Tronco.**
2. Na guia **Configuração de Tronco**, clique em **Novo** e, em seguida, clique em **Tronco do site** para criar a nova definição no escopo do site, ou **Tronco do pool** para criar as novas definições no escopo do serviço.
3. Na caixa de diálogo Selecionar um Site ou Serviço **(a** caixa de diálogo exibida dependerá se você está criando configurações com escopo de site ou escopo de serviço), selecione o local para as novas configurações e clique em **OK**.  Se a caixa de diálogo estiver em branco, isso significa que não há lugar para criar as novas configurações; por exemplo, se a caixa de diálogo Selecionar um **Site** estiver em branco, isso significa que todos os seus sites já foram atribuídos a uma coleção de sites de configuração de tronco, e cada site (e cada serviço) só poderá hospedar um conjunto desses. Nesse caso, você pode tanto excluir o conjunto existente e criar um novo conjunto ou simplesmente modificar o conjunto existente.
4. Na caixa de diálogo **Nova configuração de tronco**, faça as seleções apropriadas e clique em **OK**.
5. A propriedade **Estado** do conjunto será atualizada para **Não confirmado**. Para confirmar as alterações e para excluir o conjunto, clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
6. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
7. Na caixa **Skype for Business Painel de Controle,** clique em **OK**.
