---
title: 'Skype for Business Server: criar uma nova coleção de configurações de tronco'
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4ebd710c-38cd-4cff-9a45-df029d424580
description: 'Resumo: saiba como criar uma nova coleção de configurações de tronco usando o Painel de Controle do Skype for Business Server.'
ms.openlocfilehash: a538ad2ff5e19c21ba36afaf928144c7d255e8e2
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012325"
---
# <a name="skype-for-business-server-create-a-new-collection-of-trunk-configuration-settings"></a>Skype for Business Server: criar uma nova coleção de configurações de tronco

**Resumo:** Saiba como criar uma nova coleção de configurações de tronco usando o Painel de Controle do Skype for Business Server.
  
As configurações de tronco SIP definem a relação e os recursos entre um Servidor de Mediação e o gateway PSTN (Rede Telefônica Pública Comutado), um PBX (Branch eXchange) do IP-Public ou um Controlador de Borda de Sessão (SBC) no provedor de serviços. Estas configurações fazem coisas como especificar:
  
- Se o bypass de mídia deve ser habilitado nos troncos.
    
- As condições em que pacotes RTCP (Protocolo de Controle de Transporte em Tempo Real) são enviados.
    
- Se a criptografia SRTP (Protocolo de Transporte de Tempo Real Seguro) é necessária ou não em cada tronco.
    
Quando você instala o Skype for Business Server, uma coleção global de configurações de tronco SIP é criada para você. Além disso, os administradores podem criar conjuntos de configurações personalizadas no escopo local ou de serviço (apenas para o serviço de gateway PSTN).
  
Ao criar configurações de tronco SIP usando o Painel de Controle do Skype for Business Server, as opções a seguir estão disponíveis para você.
  
|**Configuração de UI**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.  <br/> |
|Descrição  <br/> |Descrição  <br/> |Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).  <br/> |
|Máximo de diálogos iniciais suportados  <br/> |MaxEarlyDialogs  <br/> |O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.  <br/> |
|Nível de suporte de criptografia  <br/> |SRTPMode  <br/> | Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. A configuração de mídia é definida usando os cmdlets [New-CsMediaConfiguration](/powershell/module/skype/new-csmediaconfiguration) e [Set-CsMediaConfiguration.](/powershell/module/skype/set-csmediaconfiguration) <br/>  Os valores permitidos são: <br/>  - Obrigatório: Deve se utilizar a criptografia SRTP. <br/>  - Optional: O SRTP será utilizado se o gateway lhe fornecer apoio. <br/>  Não suportado: A encriptação de SRTP não é suportada e, portanto, não será usada. <br/>  SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.<br/> |
|Suporte  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Se definido como **Habilitar endio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.  <br/> Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operados conectando a chamada da pessoa A à pessoa B).<br/> |
|Habilitar bypass de mídia  <br/> |EnableBypass  <br/> |Selecione a opção **Habilitar bypass de mídia** se você deseja que que a mídia desvie do Servidor de Mediação para processamento pelo ponto do tronco.<br/> |
|Processamento centralizado de mídia  <br/> |ConcentratedTopology  <br/> |Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)  <br/> |
|Habilitar RTP com trava  <br/> |EnableRTPLatching  <br/> |Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.  <br/> |
|Habilitar histórico de encaminhamento de chamada  <br/> |ForwardCallHistory  <br/> |Indica se as informações de histórico de chamada serão encaminhadas pelo tronco.  <br/> |
|Habilitar dados de encaminhamento P-Asserted-Identity  <br/> |ForwardPAI  <br/> |Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.  <br/> |
|Habilitar timer de failover do roteamento de saída  <br/> |EnableFastFailoverTimer  <br/> |Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.  <br/> |
|Uso associado de PSTNsages  <br/> |PSTNUsages  <br/> |Coleção de usos de PSTN atribuídos ao tronco.  <br/> |
|Número convertido para testar  <br/> |N/D  <br/> |Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.  <br/> |
|Regras de conversão associadas  <br/> |OutboundTranslationRulesList  <br/> |Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).  <br/> |
|Regras de conversão do número chamado  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Coleção de regras de conversão do número de chamada de saída atribuído ao tronco.  <br/> |
|Número de telefone a ser de testado.  <br/> |N/D  <br/> |Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.  <br/> |
|Número de chamada  <br/> |N/D  <br/> |Indica que o número de telefone a ser testado é o número do chamador.  <br/> |
|Número chamado  <br/> |N/D  <br/> |Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.  <br/> |
   
> [!NOTE]
> Os cmdlets CsTrunkConfiguration do Skype for Business Server suportam propriedades adicionais não mostradas no Painel de Controle do Skype for Business Server. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [New-CsTrunkConfiguration.](/powershell/module/skype/new-cstrunkconfiguration)
  
### <a name="to-create-new-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para criar novas configurações de tronco usando o Painel de Controle do Skype for Business Server

1. No Painel de Controle do Skype for Business Server, clique em **Roteamento** de Voz e clique em **Configuração de Tronco.**
    
2. Na guia **Configuração de Tronco**, clique em **Novo** e, em seguida, clique em **Tronco do site** para criar a nova definição no escopo do site, ou **Tronco do pool** para criar as novas definições no escopo do serviço.
    
3. Na caixa de diálogo **Selecionar um site** ou **Selecionar um serviço** (a caixa de diálogo que aparece depende se você está criando definições de escopo do site ou de escopo do serviço) selecione um local para a nova definição de configuração e, em seguida, clique em **OK**. Se a caixa de diálogo está em branco, significa que não há lugar para criar uma nova definição; por exemplo, se a caixa de diálogo **Selecionar um site** está em branco, significa que todos os sites já possuem um conjunto de sites de configuração de tronco atribuído, e cada site (e cada serviço) pode hospedar apenas um conjunto. Nesse caso, você pode tanto excluir o conjunto existente e criar um novo conjunto ou simplesmente modificar o conjunto existente.
    
4. Na caixa de diálogo **Nova configuração de tronco**, faça as seleções apropriadas e clique em **OK**.
    
5. A propriedade **Estado** do conjunto será atualizada para **Não confirmado**. Para confirmar as alterações e para excluir o conjunto, clique em **Confirmar** e, em seguida, clique em **Confirmar tudo**.
    
6. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
    
7. Na caixa de diálogo Painel de Controle do **Skype for Business Server,** clique em **OK**.
