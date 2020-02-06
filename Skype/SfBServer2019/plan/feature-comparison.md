---
title: Comparação de recursos do cliente de desktop do Skype for Business Server 2019
ms.author: jambirk
author: jambirk
ms.reviewer: PhillipGarding
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 16b14d59-7737-4f9d-aa4d-83765a18ea07
description: 'Resumo: os administradores do Skype for Business Server 2019 ou do Skype for Business Online podem usar essas tabelas para entender quais recursos são compatíveis com os clientes.'
ms.openlocfilehash: 351158dde052039ad60e796fb528af48e923dfd2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812599"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Comparação de recursos do cliente de desktop do Skype for Business Server 2019

**Resumo:** Os administradores do Skype for Business Server 2019 ou do Skype for Business Online podem usar essas tabelas para entender quais recursos são compatíveis com os clientes.

 Antes de implantar ou atualizar para o Skype for Business Server, verifique quais clientes já estão em uso em sua organização. Use as tabelas a seguir para entender o impacto do suporte a recursos nesses clientes. Isso pode ajudar você a comunicar alterações aos usuários, a acompanhar o processo de implantação e a compreender totalmente os benefícios da atualização para o cliente mais recente.

Alguns recursos disponíveis com o Skype for Business Server 2019 não estão disponíveis no Skype for Business Online; consulte [limitações da conta de usuário online ou híbrida](feature-comparison.md#Online-Hybrid) para obter informações específicas. Os administradores do Skype for Business Online podem querer consultar a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) para obter informações sobre os diferentes planos disponíveis.

As tabelas a seguir mostram os recursos que estão disponíveis em cada cliente que funciona com o Skype for Business Server 2019 ou o Skype for Business online. Você também pode consultar a comparação de [recursos de cliente móvel para o Skype for Business](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) para comparações de recursos de telefone inteligente e de cliente de Tablet. A Licença de Acesso para Cliente ou a Licença de Assinatura do Usuário que sua organização comprar também afetará os recursos que estarão disponíveis para os usuários. A implantação do cliente completo ou básico para os usuários dependerá da licença ou do plano que sua organização escolher comprar. Consulte o [Guia de licenciamento](https://products.office.com/en-us/skype-for-business/it-pros) para obter mais detalhes.

> [!IMPORTANT]
> O Skype for Business Server 2019 e o Skype for Business online são compatíveis com os seguintes clientes lançados anteriormente: Lync 2013, Skype for Business 2015 e Skype for Business 2016, bem como o cliente Skype for Business 2019. Para obter informações sobre esses clientes quando usados com outros servidores, consulte as [tabelas de comparação de clientes do Lync Server 2013](https://technet.microsoft.com/en-us/library/gg425836%28v=ocs.15%29.aspx) e do [recurso cliente de área de trabalho do Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> O aplicativo de navegador do Skype for Business Web App e o aplicativo reuniões do Skype o aplicativo Windows 10 só fornece [suporte para reuniões](feature-comparison.md#BKMK_Conferencing). Consulte [planejar clientes de reuniões (aplicativo Web e aplicativo reuniões)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) para saber mais sobre esses clientes.

## <a name="enhanced-presence-support"></a>Suporte à Presença Avançada
<a name="BKMK_EnhancedPresence"> </a>

Esta tabela abrange os recursos de Presença Avançada que vão além de uma simples indicação de que o usuário está online, offline, ocupado, etc. 


| Recurso/capacidade                                                                                  | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Publicar status                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Exibir status                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Exibir notas de status e mensagens de Ausência Temporária                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Adicionar um local personalizado                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Adicionar uma nota personalizada                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Usar uma foto de qualquer site público para Minha Imagem  <br/> (não disponível no Skype for Business online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; não oferece suporte à publicação de status com base nas informações de disponibilidade do calendário.

## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos
<a name="BKMK_Contacts"> </a>

Esta tabela abrange os recursos relacionados ao gerenciamento de contatos de IM e Presença. 


| Recurso/funcionalidade                                                                            | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Lista de contatos preenchida previamente                                                                   | &#x2714;                                      |                           |                  |
| Exibir e modificar a lista de contatos                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Marcar contatos para alertas de alteração de status                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Controlar relações de privacidade                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Pesquisar o catálogo de endereços corporativo                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Pesquisar os contatos do Microsoft Outlook                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Gerenciar grupos de contatos                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Expandir grupos de distribuição e Grupos do Office 365                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Pesquisar grupos de resposta  <br/> (não disponível no Skype for Business online)                | &#x2714;                                      |                           | &#x2714;         |
| Exibir o grupo de contatos recentes                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Exibir o grupo de conversas atuais                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Mostrar exibições de contatos alternativas (por exemplo, bloco)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Classificar contatos por grupo, relação ou novo (pessoas que adicionaram você à lista de contatos) | &#x2714;                                      |                           | &#x2714;         |
| Organizar contatos por status (disponibilidade)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Pesquisar e adicionar contatos do Exchange                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Suporte para mensagens instantâneas
<a name="BKMK_IMSupport"> </a>

Esta tabela abrange os recursos relacionados ao suporte a mensagens instantâneas.

|Recurso/funcionalidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Iniciar mensagens instantâneas ou enviar email para um contato  |&#x2714;|&#x2714;|&#x2714;|  
|Navegar entre várias conversas de IM/acompanhar várias conversas em uma única janela com guias   |&#x2714;|&#x2714;|&#x2714;| 
|Registrar conversas de IM no Outlook  |&#x2714;|&#x2714; se o histórico da conversa do lado do servidor estiver ativado   |&#x2714;|   
|Verificar a ortografia |&#x2714;|&#x2714;||   
|Pesquisa de habilidades (com integração do SharePoint Server)   <br/> (O Skype for Business Server local e o SharePoint 2013 local são necessários para a pesquisa de habilidades.)  |&#x2714;||&#x2714;|
|Integração de chat persistente (chat em grupo)  <br/> (não disponível para o Skype for Business online)|&#x2714;||&#x2714;|  
|Escalonar uma sala de chat persistente para uma reunião do Skype for Business com um clique   <br/> (não disponível para o Skype for Business online) |&#x2714;||&#x2714;| 
|Imagens embutidas do remetente e do destinatário na janela de IM |&#x2714;||&#x2714;| 
|Receber mensagens à tinta |&#x2714;||&#x2714;| 
|Definir mensagens instantâneas com alta prioridade |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Suporte para reuniões
<a name="BKMK_Conferencing"> </a>

Esta tabela abrange os recursos relacionados ao suporte a reuniões.

> [!NOTE]
>  Os recursos de reunião do Skype for Business não estão disponíveis no plano autônomo 1 do Skype for Business online.  O plano 1 está sendo [desativado](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

Nas sessões de Skype para Skype, um usuário do Skype for Business Online Plan 1 poderá participar do compartilhamento de área de trabalho e de compartilhamento de aplicativos se tiver sido convidado por um usuário que tem acesso aos recursos de compartilhamento.
Para obter detalhes, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx). 

|Recurso/funcionalidade | Cliente Skype for Business 2016 | Skype for Business para Mac | Skype for Business Web App | Cliente Skype for Business 2015 | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Adicionar áudio do computador  |&#x2714;|&#x2714;|&#x2714; (requer plug-in)  |&#x2714;|&#x2714;| 
|Adicionar vídeo |&#x2714;|&#x2714;|&#x2714; (requer plug-in) |&#x2714;|&#x2714;| 
|Exibir vídeo com vários participantes (modo de exibição de galeria)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhamento de tela baseado em vídeo    |&#x2714;|&#x2714;|&#x2714; somente exibição   ||| 
|Usar os controles do apresentador na reunião |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Acessar a lista de participantes detalhada da reunião |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Participar de IM com vários participantes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Compartilhar a área de trabalho (se habilitado)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (requer plug-in) |&#x2714;| &#x2714;|
|Compartilhar um programa (se habilitado) |&#x2714;|Somente exibição   |&#x2714; (requer plug-in)  |&#x2714;|&#x2714;|   
|Adicionar participantes anônimos (se habilitado) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar as reuniões de áudio discada &#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Iniciar uma reunião do tipo Reunir Agora|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Adicionar e apresentar arquivos do Microsoft PowerPoint |&#x2714;| &#x2778; anotações não estão disponíveis   |&#x2714;|&#x2714;|&#x2714;| 
|Navegar por arquivos do Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Usar e editar notas de reunião do OneNote  |&#x2714;||Somente editar (sem adicionar)  |&#x2714;|&#x2714;|
|Usar um quadro de comunicações |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Realizar votações |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Carregar arquivos para compartilhar com outras pessoas |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Agendar um reunião ou conferência |Agendador do Outlook ou Skype for Business Web  |Agendador do Outlook ou Skype for Business Web |Agendador da Web do Skype for Business |Agendador do Outlook ou Skype for Business Web   |Agendador do Outlook ou Lync Web |  
|P&amp;um gerente |&#x2714;|||||
|Desabilitar vídeo de participante |&#x2714;||&#x2714;|||
|Desabilitar mensagens instantâneas de reunião |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Ativar mudo da audiência |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Tornar todos participantes |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Produzir Transmissão de Reunião do Skype |&#x2714;|||||
|O representante pode agendar uma reunião em nome do delegador |&#x2714;|&#x2714;|&#x2714;|||
|Sincronizar representantes entre o Skype for Business e o Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Definir Destaque de Vídeo (bloquear vídeo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Conceder/cancelar controle de compartilhamento de tela  |&#x2714;||&#x2714;|||

 &#x2776; participantes não podem controlar áreas de trabalho que são compartilhadas pelos usuários do Skype for Business no Mac, Lync para Mac 2011 ou Communicator para Mac 2011. Skype for Business no Mac, Lync para Mac 2011 e Communicator para Mac 2011 os usuários não podem controlar áreas de trabalho compartilhadas por usuários do Windows. Isso também não funcionará para o Skype for Business Web App no máximo OSX.

 &#x2777; para o Skype for Business Online, esse recurso requer a conferência PSTN da Microsoft, a Unificação de mensagens do Exchange ou um provedor de serviços de audioconferência de terceiros.

 &#x2778; o cliente do Lync for Mac 2011 não pode exibir apresentações do PowerPoint do Microsoft Office 2013 quando foram compartilhados em uma conferência pelo Skype for Business Web App.

&#x2779; para aplicativos Skype for Business 2016, você deve usar o clique para executar, a compilação 16.0.4227 ou posterior.

&#x2780; para aplicativos Skype for Business 2015, você deve ter a atualização de setembro, compilação 15.0.4747 ou posterior.

## <a name="voice-telephony-support"></a>Suporte para voz (telefonia)
<a name="BKMK_Telephony"> </a>

Esta tabela abrange os recursos relacionados ao suporte a serviços de voz.

> [!NOTE]
> Os recursos de voz do Skype for Business (telefonia) são limitados a certos planos de assinatura do Skype for Business online. Para obter detalhes, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx). 

 | Recurso/funcionalidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----| 
|Iniciar uma chamada |&#x2714;|&#x2714;|&#x2714;|
|Clicar para ligar para um contato |&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada |&#x2714;|&#x2714;|&#x2714;|  
|Gerenciar o encaminhamento de chamadas |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Gerenciar configurações de chamadas de equipe |&#x2714;||&#x2714; &#x2776; |
|Gerenciar representantes |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Iniciar uma chamada para um Grupo de Resposta|&#x2714;||&#x2714; &#x2776; |
|Suporte a serviços de emergência (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Notificação de IM para URI (s) SIP para chamada E-911 |&#x2714;|&#x2714;|&#x2714;|
|Notificação de IM para a lista de distribuição para a chamada E-911|&#x2714;|&#x2714;|&#x2714;|
|Conectar-se à caixa postal, configurar ou alterar a saudação |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Notificação de chamada perdida |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Realizar chamadas em nome de outro contato (cenário de gerente/representante) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Atender chamadas de outras pessoas se configurado como representante |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Estacionamento de chamada |&#x2714;||&#x2714; &#x2776; |
|Recebimento de chamadas em grupo |&#x2714;||&#x2714; &#x2776; |
|Roteamento com base no local |&#x2714;|&#x2714;|&#x2714;| 
|Gerenciar Grupo de chamada de equipe/Grupo de Resposta |&#x2714;||&#x2714;|

 &#x2776; este recurso não está disponível no Skype for Business online.

## <a name="external-users-support"></a>Suporte para usuários externos
<a name="BKMK_ExternalUsers"> </a>

Esta tabela abrange os recursos relacionados ao suporte a usuários externos hospedados na PSTN.


|Recurso/funcionalidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Iniciar IM com um contato público |&#x2714;|&#x2714;|&#x2714;| 
|Iniciar IM com um contato federado |&#x2714;|&#x2714;|&#x2714;| 
|Realizar chamadas de dois ou vários participantes com usuários externos  <br/> (não disponível no Skype for Business online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Suporte a gravação
<a name="BKMK_Recording"> </a>

Esta tabela abrange os recursos relacionados ao suporte à gravação de reuniões.

| Recurso/funcionalidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |   
|:-----|:-----|:-----|:-----|  
|Gravação de áudio e vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado no lado do cliente |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Gravação de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint do lado do cliente| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Selecionar a resolução de gravação preferencial  |&#x2714;||&#x2714;|

 &#x2776; gravação não está disponível em determinados planos autônomos do Skype for Business online. A gravação exige direitos do cliente completo do Skype for Business.

 &#x2777; gravação de transferências de arquivo, páginas compartilhadas do OneNote e anotações do PowerPoint não está disponível no Skype for Business online.

## <a name="modern-authentication"></a>Autenticação moderna
<a name="BKMK_Recording"> </a>

Essa tabela abrange os recursos que precisam de suporte à autenticação moderna. 

A autenticação moderna também exige uma topologia descrita nas [topologias do Skype for Business com suporte à autenticação moderna](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Recurso/funcionalidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Autenticação moderna |&#x2714;|&#x2714;|&#x2714;|
|Autenticação multifator|&#x2714;|&#x2714;|&#x2714;|
|Autenticação baseada em certificado |&#x2714; (somente dispositivo associado a um domínio) |&#x2714;|&#x2714; (somente dispositivo associado a um domínio)  |
|Autenticação Kerberos |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Suporte a arquivamento, conformidade e logs
<a name="BKMK_Archiving"> </a>

Esta tabela abrange os recursos relacionados ao suporte a funções de arquivamento e registro em log.


 | Recurso/capacidade | Cliente do Skype for Business 2015, 2016 ou 2019 | Skype for Business para Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Arquivamento de conversas de IM no Histórico da Conversa do Outlook|&#x2714; &#x2776; |&#x2714; se o histórico da conversa do lado do servidor estiver ativado  |&#x2714; &#x2776; | 
|Arquivamento do compartilhamento de áudio, vídeo e aplicativos, do compartilhamento de área de trabalho e do conteúdo carregado do lado do cliente  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Arquivamento do lado do cliente de transferências de arquivo, páginas compartilhadas do OneNote e anotações do PowerPoint (não disponível no Skype for Business online)  |&#x2714;||&#x2714;|
|Acessar os logs de entrada do ícone do Skype for Business na barra de tarefas |&#x2714;||&#x2714;|

 &#x2776; para usuários do Skype for Business Online, esse recurso requer o Exchange Online e é controlado pelo atributo de bloqueio de caixa de correio in-loco do usuário do Exchange.

## <a name="client-limitations"></a>Limitações do cliente 
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitações do cliente básico
<a name="Full-Basic"> </a>

Os recursos a seguir estão disponíveis com o cliente completo e não estão disponíveis com o cliente básico:  

- Gerenciar configurações de chamada de equipe

- Gerenciar representantes

- Realizar chamadas em nome de outro contato (cenário de gerente/representante)

- Atender chamadas de outras pessoas se configurado como um representante

- Gerenciar volume alto de chamadas

- Iniciar uma chamada para um Grupo de Resposta

- Estacionamento de chamada

- Alterar saudação

- Recebimento de chamadas em grupo

### <a name="online-or-hybrid-user-account-limitations"></a>Limitações de conta de usuário online ou híbrida
<a name="Online-Hybrid"> </a>

As contas do usuário podem existir online ou no local e isso afetará os recursos que estarão disponíveis para aquele usuário. Os usuários com contas no Skype for Business online não terão acesso aos recursos a seguir, mesmo com o cliente completo: 

- Presença avançada: usar uma foto de qualquer site público para Minha Imagem.

- Contatos: pesquisar grupos de resposta.

- Suporte para mensagens instantâneas: integração de chat persistente (chat em grupo).

- Suporte a IM: escalonar uma sala de chat persistente para uma reunião do Skype for Business com um clique

- Usuários externos: realizar chamadas de dois ou vários participantes com usuários externos.

## <a name="see-also"></a>Confira também
<a name="Types"> </a>

[Planejar clientes e dispositivos](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Atualizações mais recentes das versões do Skype for Business que usam o Windows Installer (MSI)](../../SfbServer/sfb-client-updates.md)
