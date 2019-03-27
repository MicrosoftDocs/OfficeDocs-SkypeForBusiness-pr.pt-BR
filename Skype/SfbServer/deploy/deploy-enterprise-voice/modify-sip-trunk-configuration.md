---
title: Modificar as definições de configuração de tronco SIP no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7d68b09c-9ea0-43bd-997c-df887869d607
description: 'Resumo: Saiba como modificar as definições de configuração de tronco SIP usando o Skype para painel de controle do servidor de negócios.'
ms.openlocfilehash: 6fbae1279ec1734cd67269651c65dc7c278ca3a3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898695"
---
# <a name="modify-sip-trunk-configuration-settings-in-skype-for-business-server"></a>Modificar as definições de configuração de tronco SIP no Skype para Business Server
 
**Resumo:** Saiba como modificar as definições de configuração de tronco SIP usando o Skype para painel de controle do servidor de negócios.
  
As configurações do tronco SIP definem o relacionamento e as capacidades entre um Servidor de Mediação e o gateway da Rede Telefônica Pública Comutada (PSTN), uma Central Privada de Comutação de IP (PBX) ou um Controlador de Borda de Sessão (SBC) no provedor de serviço. Essas configurações realizam atividades como especificar:
  
- Se o desvio de mídia deve ser ativado nos troncos.
    
- As condições em que os pacotes do Protocolo de Controle de Transporte em Tempo Real (RTCP) são enviados.
    
- Se é necessário criptografia de Protocolo de Transporte Seguro em Tempo Real (SRTP) em cada tronco.
    
Quando você instala o Skype para Business Server, uma coleção global de definições de configuração de tronco SIP é criada para você. Além disso, os administradores podem criar coleções de configurações personalizadas no escopo do site ou no escopo do serviço (somente para o serviço de gateway PSTN). Qualquer uma dessas coleções podem serem modificada posteriormente usando qualquer um dos Skype para painel de controle de servidor de negócios ou Skype para Business Server Management Shell.
  
Ao modificar as definições de configuração de tronco SIP usando Skype para painel de controle do Business Server, as seguintes opções estão disponíveis para você.
  
|**Configuração de UI**|**Parâmetro do PowerShell**|**Descrição**|
|:-----|:-----|:-----|
|Nome  <br/> |Identidade  <br/> |Identificador exclusivo para a coleção. Esta propriedade é somente leitura; não é possível modificar a Identidade de uma coleção de configurações do tronco.  <br/> |
|Descrição  <br/> |Descrição  <br/> |Fornece uma forma para os administradores armazenarem informações sobre as configurações (por exemplo, o motivo da configuração do tronco).  <br/> |
|Máximo de diálogos iniciais suportados  <br/> |MaxEarlyDialogs  <br/> |O número máximo de respostas bifurcadas que um Gateway PSTN, IP-PBX ou SBC no Provedor de serviços pode receber em resposta a um convite que ele enviou ao Servidor de mediação.  <br/> |
|Nível de suporte de criptografia  <br/> |SRTPMode  <br/> | Indica o nível de suporte para proteção do tráfego de mídia entre o Servidor de Medicação e o Gateway de PSTN, IP-PBX ou SBC no provedor de serviços. Para casos de bypass de mídia, esse valor deve ser compatível com a configuração EncryptionLevel na configuração de mídia. Configuração de mídia for definida usando os cmdlets [New-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csmediaconfiguration?view=skype-ps) e [Set-CsMediaConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csmediaconfiguration?view=skype-ps) . <br/>  Os valores permitidos são: <br/>  - Obrigatório: Deve se utilizar a criptografia SRTP. <br/>  - Optional: O SRTP será utilizado se o gateway lhe fornecer apoio. <br/>  Não suportado: A encriptação de SRTP não é suportada e, portanto, não será usada. <br/>  SRTPMode é usado apenas se o gateway estiver configurado para usar a Segurança da Camada de Transporte (TLS). Se o gateway estiver configurado com o Protocolo de Controle de Transmissão (TCP) como transporte, SRTPMode será internamente definido como NotSupported.<br/> |
|Suporte  <br/> |Enable3pccRefer  <br/> EnableReferSupport  <br/> |Se definido como **Habilitar envio ao gateway**, indica que o tronco suporta receber solicitações de Refer do Servidor de Mediação.  <br/> Se definido como **Habilitar refer usando controle de chamada terceirizado**, indica que o protocolo 3pcc pode ser usado para permitir que chamadas transferidas pulem o local host. 3pcc também é conhecido como "controle terceirizado" e ocorre quando um terceiro é usado para conectar dois chamadores (por exemplo, um operador conectando a chamada da pessoa A à pessoa B).<br/> |
|Habilitar bypass de mídia  <br/> |EnableBypass  <br/> |Indica se o bypass de mídia foi habilitado para esse tronco. O bypass de mídia só pode ser habilitado se **Processamento centralizado de mídia** também for habilitado.<br/> |
|Processamento centralizado de mídia  <br/> |ConcentratedTopology  <br/> |Indica se é um ponto conhecido de término de mídia (Um exemplo de ponto de terminação de mídia conhecido seria um Gateway PSTN, em que a terminação de mídia possui o mesmo IP que a terminação de sinalização.)  <br/> |
|Habilitar RTP com trava  <br/> |EnableRTPLatching  <br/> |Indica se os troncos SIP suportam ou não trava de RTP. Trava de RTP é uma tecnologia que habilita a conectividade de RTP/RTCP por dispositivo NAT (conversão de endereço de rede) ou firewall.  <br/> |
|Habilitar histórico de encaminhamento de chamada  <br/> |ForwardCallHistory  <br/> |Indica se as informações do histórico de chamada serão encaminhadas por meio do tronco.  <br/> |
|Habilitar dados de encaminhamento P-Asserted-Identity  <br/> |ForwardPAI  <br/> |Indica se o header de P-Asserted-Identity (PAI) será encaminhado junto com a chamada. O header PAI oferece uma forma de verificar a identidade do chamador.  <br/> |
|Habilitar timer de failover do roteamento de saída  <br/> |EnableFastFailoverTimer  <br/> |Indica se chamadas de saída não atendidas pelo gateway em 10 segundos serão roteadas ao próximo tronco disponível; se não houver troncos adicionais, a chamada cairá automaticamente. Em uma empresa com redes e respostas de gateway lentas, que poderia resultar em chamadas desligadas desnecessariamente.  <br/> |
|Uso associado de PSTNsages  <br/> |PSTNUsages  <br/> |Conjunto de usos PSTN atribuídos ao tronco.  <br/> |
|Número convertido para testar  <br/> |N/D  <br/> |Número de telefone que pode ser usado para um teste ad hoc de configurações do tronco.  <br/> |
|Regras de conversão associadas  <br/> |OutboundTranslationRulesList  <br/> |Coleção de regras de conversão de números de telefone que se aplicam a chamadas tratadas pelo Roteamento de saída (chamadas roteadas para destinos de PBX ou PSTN).  <br/> |
|Regras de conversão do número chamado  <br/> |OutboundCallingNumberTranslationRulesList  <br/> |Conjunto de regras de conversão de número de chamada de saída atribuídas ao tronco.  <br/> |
|Número de telefone a ser de testado.  <br/> |N/D  <br/> |Número de telefone que pode ser usado para um teste ad hoc das regras de conversão.  <br/> |
|Número de chamada  <br/> |N/D  <br/> |Indica que o número de telefone a ser testado é o número do chamador.  <br/> |
|Número chamado  <br/> |N/D  <br/> |Indica que o número de telefone a ser testado é o número da pessoa sendo chamada.  <br/> |
   
> [!NOTE]
> Os cmdlets do Lync Server CsTrunkConfiguration suporte a propriedades adicionais não são mostradas no painel de controle do Lync Server. Para obter mais informações, consulte o tópico de ajuda para o cmdlet [Set-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cstrunkconfiguration?view=skype-ps) .
  
### <a name="to-modify-sip-trunk-configuration-settings-by-using-skype-for-business-server-control-panel"></a>Para modificar as definições de configuração de tronco SIP usando Skype para o painel de controle do servidor de negócios

1. No painel de controle do servidor de negócios do Skype, clique em **Roteamento de voz**e clique em **Configuração de tronco**.
    
2. Na guia **Configuração de Tronco**, clique duas vezes nas configurações do tronco a ser modificado. Observe que é possível editar somente uma coleção de configurações por vez. Se quiser fazer as mesmas alterações em múltiplas coleções, use Windows PowerShell.
    
3. Na caixa de diálogo **Editar Configuração de Tronco**, faça as seleções apropriadas e clique em **OK**.
    
4. A propriedade **Estado** da coleção será atualizada para **Não vinculado**. Para vincular as alterações e excluir a coleção, clique em **Vincular** e em **Vincular tudo**.
    
5. Na caixa de diálogo **Configurações de Voz Não Vinculadas**, clique em **OK**.
    
6. Na caixa de diálogo **Skype para painel de controle do Business Server** , clique em **Okey**.
    

