---
title: Comparação de recursos do cliente de desktop para o Skype for Business Server 2019
ms.author: v-lanac
author: LanaChin
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
description: 'Resumo: os administradores do Skype for Business Server 2019 ou do Skype for Business Online podem usar essas tabelas para compreender quais recursos são compatíveis com os clientes.'
ms.openlocfilehash: f8b50614d663104e1307b233449ccffc0e26adb5
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42129484"
---
# <a name="desktop-client-feature-comparison-for-skype-for-business-server-2019"></a>Comparação de recursos do cliente de desktop para o Skype for Business Server 2019

**Resumo:** Os administradores do Skype for Business Server 2019 ou do Skype for Business Online podem usar essas tabelas para compreender quais recursos são compatíveis com os clientes.

 Antes de implantar ou atualizar para o Skype for Business Server, verifique quais clientes já estão em uso na sua organização. Use as tabelas abaixo para entender o impacto do suporte a recursos nesses clientes. Isso pode ajudar você a comunicar alterações aos usuários, ajustar o processo de implantação e compreender totalmente os benefícios da atualização para o cliente mais recente.

Alguns recursos disponíveis com o Skype for Business Server 2019 não estão disponíveis no Skype for Business Online; Confira [limitações da conta de usuário online ou híbrida](feature-comparison.md#Online-Hybrid) para obter informações específicas. Os administradores do Skype for Business Online podem querer consultar a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/skype-for-business-online-service-description.aspx) para obter informações sobre os diferentes planos disponíveis para eles.

As tabelas a seguir mostram os recursos disponíveis em cada cliente que funciona com o Skype for Business Server 2019 ou o Skype for Business online. Você também pode querer consultar a [comparação de recursos do cliente móvel para o Skype for Business](../../SfbServer/plan-your-deployment/clients-and-devices/mobile-feature-comparison.md) para comparações de recursos de telefone inteligente e cliente do Tablet. A licença de acesso para cliente ou a licença de assinatura de usuário que sua organização comprar também terá um impacto sobre quais recursos estão disponíveis para os usuários. Se você implantar o cliente completo ou básico para os usuários depende da licença ou do plano escolhido para comprar. Consulte o [Guia de licenciamento](https://products.office.com/skype-for-business/it-pros) para obter mais detalhes.

> [!IMPORTANT]
> O Skype for Business Server 2019 e o Skype for Business online dão suporte aos seguintes clientes lançados anteriormente: Lync 2013, Skype for Business 2015 e Skype for Business 2016, bem como o cliente do Skype for Business 2019. Para obter informações sobre esses clientes quando usados com outros servidores, consulte as [tabelas de comparação de clientes para o Lync Server 2013](https://technet.microsoft.com/library/gg425836%28v=ocs.15%29.aspx) e [a comparação de recursos do cliente de desktop do Skype for Business 2015](../../SfbServer/plan-your-deployment/clients-and-devices/desktop-feature-comparison.md). 


> [!NOTE]
> O aplicativo de navegador do Skype for Business Web App e o aplicativo Windows 10 do aplicativo de reuniões do Skype oferecem suporte apenas a [reuniões](feature-comparison.md#BKMK_Conferencing). Consulte [Plan for encontros clients (aplicativo Web e aplicativos de reuniões)](../../SfbServer/plan-your-deployment/clients-and-devices/meetings-clients.md) para obter mais informações sobre esses clientes.

## <a name="enhanced-presence-support"></a>Suporte de presença avançada
<a name="BKMK_EnhancedPresence"> </a>

Esta tabela abrange os recursos de presença avançada que vão além de uma simples indicação de se um usuário está online, offline, ocupado, etc. 


| Recurso/capacidade                                                                                  | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |
|:----------------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Status de publicação                                                                                      | &#x2714;                                      | &#x2714; &#x2776;         | &#x2714;         |
| Exibir status                                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Exiba as notas de status e as mensagens Fora do Escritório                                                        | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Adicione um local personalizado                                                                               | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Adicione uma nota personalizada                                                                                   | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Usar uma foto de qualquer site público para minha imagem  <br/> (não disponível no Skype for Business online) | &#x2714;                                      |                           | &#x2714;         |

 &#x2776; não suporta o status de publicação com base nas informações de disponibilidade do calendário.

## <a name="contacts-and-contact-groups-support"></a>Suporte para contatos e grupos de contatos
<a name="BKMK_Contacts"> </a>

Esta tabela abrange os recursos relacionados ao gerenciamento de contatos de mensagens instantâneas e presença. 


| Recurso/capacidade                                                                            | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |
|:----------------------------------------------------------------------------------------------|:----------------------------------------------|:--------------------------|:-----------------|
| Lista de contatos preenchida previamente                                                                   | &#x2714;                                      |                           |                  |
| Exibir e modificar a lista de contatos                                                                 | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Marque os contatos para alertas de alteração do status                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Controle as relações de privacidade                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Pesquise na agenda corporativa                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Pesquise os contatos do Microsoft Outlook                                                             | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Gerencie os grupos de contatos                                                                         | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Expandir grupos de distribuição e grupos do Office 365                                              | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Pesquise os Grupos de Respostas  <br/> (não disponível no Skype for Business online)                | &#x2714;                                      |                           | &#x2714;         |
| Exiba o grupo de contatos recentes                                                                 | &#x2714;                                      |                           | &#x2714;         |
| Exiba o grupo de conversas atuais                                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Mostre as exibições de contato alternativas (por exemplo, lado a lado)                                           | &#x2714;                                      | &#x2714;                  | &#x2714;         |
| Classificar contatos por grupo, relação ou novo (pessoas que adicionaram você à lista de contatos) | &#x2714;                                      |                           | &#x2714;         |
| Classificar contatos por status (disponibilidade)                                                        | &#x2714;                                      |                           | &#x2714;         |
| Pesquisar e adicionar contatos do Exchange                                                              | &#x2714;                                      |                           | &#x2714;         |

## <a name="im-support"></a>Suporte a mensagens instantâneas
<a name="BKMK_IMSupport"> </a>

Esta tabela abrange os recursos relacionados ao suporte a mensagens instantâneas.

|Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Iniciar IM com ou email para um contato  |&#x2714;|&#x2714;|&#x2714;|  
|Navegar entre várias conversas de mensagens instantâneas/acompanhar várias conversas em uma única janela com guias   |&#x2714;|&#x2714;|&#x2714;| 
|Registre as conversas de IM no Outlook  |&#x2714;|&#x2714; se o histórico da conversa do servidor estiver ativado   |&#x2714;|   
|Verificar ortografia |&#x2714;|&#x2714;||   
|Pesquisa de habilidades (com a integração do SharePoint Server)  <br/> (O Skype for Business Server local e o SharePoint 2013 local são necessários para pesquisa de habilidades.)  |&#x2714;||&#x2714;|
|Integração de chat persistente (chat em grupo)  <br/> (não está disponível para o Skype for Business online)|&#x2714;||&#x2714;|  
|Escalonar uma sala de chat persistente para uma reunião do Skype for Business com um clique  <br/> (não está disponível para o Skype for Business online) |&#x2714;||&#x2714;| 
|Imagens embutidas do remetente e do destinatário na janela de mensagens instantâneas |&#x2714;||&#x2714;| 
|Receber mensagens à tinta |&#x2714;||&#x2714;| 
|Definir mensagens INSTANTÂNEAs como alta prioridade |&#x2714;||&#x2714;|

## <a name="meetings-support"></a>Suporte a reuniões
<a name="BKMK_Conferencing"> </a>

Esta tabela abrange os recursos relacionados ao suporte a reuniões.

> [!NOTE]
>  Os recursos de reunião do Skype for Business não estão disponíveis no Skype for Business Online, plano autônomo 1.  O plano 1 está sendo [desativado](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-for-business-online-plan-1-retirement
).

Em sessões do Skype para Skype, um usuário do plano 1 do Skype for Business online pode participar do compartilhamento de área de trabalho e compartilhamento de aplicativos se eles forem convidados por um usuário que tenha acesso aos recursos de compartilhamento.
Para obter detalhes, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx). 

|Recurso/capacidade | Cliente 2016 do Skype for Business | Skype for Business no Mac | Skype for Business Web App | Cliente 2015 do Skype for Business | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|:-----|:-----|  
|Adicione áudio de computador  |&#x2714;|&#x2714;|&#x2714; (exige plug-in)  |&#x2714;|&#x2714;| 
|Adicione vídeo |&#x2714;|&#x2714;|&#x2714; (exige plug-in) |&#x2714;|&#x2714;| 
|Exibir vídeo de vários participantes (modo de exibição de galeria)  |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Compartilhamento de tela baseado em vídeo    |&#x2714;|&#x2714;|&#x2714; somente exibição   ||| 
|Use controles de apresentador durante a reunião |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Acesse a lista da reunião detalhada |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Participe de IM com várias partes |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|  
|Compartilhe a área de trabalho (se ativado)  |&#x2714;|&#x2714; &#x2776; |&#x2714; &#x2776;  (exige plug-in) |&#x2714;| &#x2714;|
|Compartilhe um programa (se ativado) |&#x2714;|Somente exibição   |&#x2714; (exige plug-in)  |&#x2714;|&#x2714;|   
|Adicione participantes anônimos (se ativado) |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Usar reuniões de áudio discada &#x2777;|&#x2714; |&#x2714;|&#x2714;  |&#x2714;|&#x2714;  |
|Iniciar uma reunião agora|&#x2714;|&#x2714;||&#x2714;|&#x2714;|  
|Adicione e apresente arquivos do Microsoft PowerPoint |&#x2714;| &#x2778; anotações não estão disponíveis   |&#x2714;|&#x2714;|&#x2714;| 
|Navegar arquivos do Microsoft PowerPoint |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;| 
|Adicionar e editar anotações de reunião do OneNote  |&#x2714;||Somente edição (não adicionar)  |&#x2714;|&#x2714;|
|Use um quadro de avisos |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Faça votações |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Carregar arquivos para compartilhar com outras pessoas |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Programe uma reunião ou conferência |Agendador da Web do Outlook ou Skype for Business  |Agendador da Web do Outlook ou Skype for Business |Agendador da Web do Skype for Business |Agendador da Web do Outlook ou Skype for Business   |Agendador do Outlook ou do Lync Web |  
|P&amp;um gerente |&#x2714;|||||
|Desabilitar vídeo de participante |&#x2714;||&#x2714;|||
|Desabilitar IM de reunião |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Audiência sem áudio |&#x2714;|&#x2714;|&#x2714;|&#x2714;|&#x2714;|
|Tornar todos um participante |&#x2714;||&#x2714;|&#x2714;|&#x2714;|
|Produzir transmissão de reunião do Skype |&#x2714;|||||
|O representante pode agendar uma reunião em nome da delegação |&#x2714;|&#x2714;|&#x2714;|||
|Sincronizar representantes entre o Skype for Business e o Outlook |&#x2714;||&#x2714;|&#x2714;|| 
|Definir vídeo Spotlight (bloquear vídeo) |&#x2714;||&#x2714;|&#x2714;|&#x2714;| 
|Conceder/assumir controle de compartilhamento de tela  |&#x2714;||&#x2714;|||

 &#x2776; os participantes não podem controlar áreas de trabalho compartilhadas pelo Skype for Business no Mac, Lync para Mac 2011 ou Communicator para Mac 2011 users. Skype for Business no Mac, Lync para Mac 2011 e Communicator para Mac 2011 os usuários não podem controlar áreas de trabalho compartilhadas por usuários do Windows. Isso também não funciona para o Skype for Business Web App no máximo OSX.

 &#x2777; para o Skype for Business Online, esse recurso exige conferências PSTN da Microsoft, Unificação de mensagens do Exchange ou um provedor de audioconferência de terceiros.

 &#x2778; o cliente do Lync para Mac 2011 não pode exibir apresentações do PowerPoint do Microsoft Office 2013 quando elas tiverem sido compartilhadas em uma conferência pelo Skype for Business Web App.

&#x2779; para aplicativos do Skype for Business 2016, você deve usar clique para executar, compilar 16.0.4227 ou posterior.

&#x2780; para aplicativos do Skype for Business 2015, você deve ter a atualização de setembro, criar 15.0.4747 ou posterior.

## <a name="voice-telephony-support"></a>Suporte a voz (telefonia)
<a name="BKMK_Telephony"> </a>

Esta tabela abrange os recursos relacionados ao suporte a serviços de voz.

> [!NOTE]
> Os recursos de voz do Skype for Business (telefonia) são limitados a determinados planos de assinatura do Skype for Business online. Para obter detalhes, consulte a [Descrição do serviço do Skype for Business online](https://technet.microsoft.com/library/jj822172.aspx). 

 | Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----| 
|Iniciar uma chamada |&#x2714;|&#x2714;|&#x2714;|
|Clique para chamar um contato |&#x2714;|&#x2714;|&#x2714;|
|Transferir uma chamada |&#x2714;|&#x2714;|&#x2714;|  
|Gerencie o redirecionamento de chamada |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Gerenciamento de configurações de chamada em equipe |&#x2714;||&#x2714; &#x2776; |
|Gerenciamento de delegados |&#x2714;|&#x2714;   |&#x2714; &#x2776; |
|Iniciação de uma chamada para um Grupo de Resposta|&#x2714;||&#x2714; &#x2776; |
|Suporte para serviços de emergência (E-911) |&#x2714;|&#x2714; |&#x2714; &#x2776; |
|Notificação de IM para URI (s) SIP para chamada E-911 |&#x2714;|&#x2714;|&#x2714;|
|Notificação de IM para a lista de distribuição para a chamada E-911|&#x2714;|&#x2714;|&#x2714;|
|Conectar-se à caixa postal, configurar ou alterar saudação |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Notificação de chamada perdida |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Realização de chamadas em nome de outro contato (cenário gerente/delegado) |&#x2714;|&#x2714;|&#x2714; &#x2776; |
|Administração de chamadas de terceiros quando configurado como delegado |&#x2714;|&#x2714;|&#x2714; &#x2776; | 
|Estacionamento de chamada |&#x2714;||&#x2714; &#x2776; |
|Atendimento de chamadas de grupo |&#x2714;||&#x2714; &#x2776; |
|Roteamento com base no local |&#x2714;|&#x2714;|&#x2714;| 
|Gerenciar grupo de resposta/grupo de chamada de equipe |&#x2714;||&#x2714;|

 &#x2776; este recurso não está disponível no Skype for Business online.

## <a name="external-users-support"></a>Suporte a usuários externos
<a name="BKMK_ExternalUsers"> </a>

Esta tabela abrange os recursos relacionados ao suporte a usuários externos hospedados no PSTN.


|Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Iniciar o IM com um contato público |&#x2714;|&#x2714;|&#x2714;| 
|Iniciar o IM com um contato federado |&#x2714;|&#x2714;|&#x2714;| 
|Realizar chamadas de duas ou várias partes com usuários externos  <br/> (não disponível no Skype for Business online)  |&#x2714;|&#x2714;|&#x2714;| 

## <a name="recording-support"></a>Suporte à gravação
<a name="BKMK_Recording"> </a>

Esta tabela abrange os recursos relacionados ao suporte à gravação de reuniões.

| Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |   
|:-----|:-----|:-----|:-----|  
|Gravação de áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado do lado do cliente |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Gravação do lado do cliente de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint| &#x2714; &#x2777; ||&#x2714; &#x2777; |
|Selecionar resolução de gravação preferencial  |&#x2714;||&#x2714;|

 &#x2776; gravação não está disponível em determinados planos autônomos do Skype for Business online. A gravação exige direitos de cliente completo do Skype for Business.

 &#x2777; gravação de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint não está disponível no Skype for Business online.

## <a name="modern-authentication"></a>Autenticação moderna
<a name="BKMK_Recording"> </a>

Esta tabela abrange os recursos que exigem suporte para a autenticação moderna. 

A autenticação moderna também requer uma topologia descrita nas [topologias do Skype for Business compatíveis com a autenticação moderna](../../SfbServer/plan-your-deployment/modern-authentication/topologies-supported.md).


 | Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 | 
|:-----|:-----|:-----|:-----|  
|Autenticação moderna |&#x2714;|&#x2714;|&#x2714;|
|Autenticação multifator|&#x2714;|&#x2714;|&#x2714;|
|Autenticação baseada em certificado |&#x2714; (somente dispositivo ingresso no domínio) |&#x2714;|&#x2714; (somente dispositivo ingresso no domínio)  |
|Autenticação Kerberos |&#x2714;||&#x2714;|

## <a name="archiving-compliance-and-logging-support"></a>Suporte a arquivamento, conformidade e log
<a name="BKMK_Archiving"> </a>

Esta tabela abrange os recursos relacionados ao suporte a funções de arquivamento e registro em log.


 | Recurso/capacidade | Cliente 2015, 2016 ou 2019 do Skype for Business | Skype for Business no Mac | Cliente do Lync 2013 |  
|:-----|:-----|:-----|:-----|  
|Arquivamento de conversas de IM no histórico de conversas do Outlook|&#x2714; &#x2776; |&#x2714; se o histórico da conversa do servidor estiver ativado  |&#x2714; &#x2776; | 
|Arquivamento de áudio, vídeo, compartilhamento de aplicativos, compartilhamento de área de trabalho e conteúdo carregado do lado do cliente  |&#x2714; &#x2776; ||&#x2714; &#x2776; |
|Arquivamento no cliente de transferências de arquivos, páginas compartilhadas do OneNote e anotações do PowerPoint (não disponível no Skype for Business online)  |&#x2714;||&#x2714;|
|Acessar os logs de entrada do ícone do Skype for Business na barra de tarefas |&#x2714;||&#x2714;|

 &#x2776; para usuários do Skype for Business Online, esse recurso exige o Exchange Online e é controlado pelo atributo de bloqueio in-loco da caixa de correio do Exchange do usuário.

## <a name="client-limitations"></a>Limitações do cliente
<a name="Types"> </a>

### <a name="basic-client-limitations"></a>Limitações básicas de cliente
<a name="Full-Basic"> </a>

Os recursos a seguir estão disponíveis usando o cliente completo e não estão disponíveis com o cliente básico: 

- Gerenciamento de configurações de chamada em equipe

- Gerenciamento de delegados

- Realização de chamadas em nome de outro contato (cenário gerente/delegado)

- Administração de chamadas de terceiros quando configurado como delegado

- Gerenciamento de um alto volume de chamadas

- Iniciação de uma chamada para um Grupo de Resposta

- Estacionamento de chamada

- Alterar saudação

- Atendimento de chamadas de grupo

### <a name="online-or-hybrid-user-account-limitations"></a>Limitações da conta de usuário online ou híbrida
<a name="Online-Hybrid"> </a>

As contas de usuário podem existir online ou no local, e isso afetará os recursos disponíveis para esse usuário. Os usuários com contas no Skype for Business online não terão acesso aos seguintes recursos, mesmo com o cliente completo: 

- Presença avançada: usar uma foto de qualquer site público para minha imagem

- Contatos: Pesquisar grupos de resposta

- Suporte de IM: integração de chat persistente (chat em grupo)

- Suporte de IM: escalonar uma sala de chat persistente para uma reunião do Skype for Business com um clique

- Usuários externos: conduzir chamadas de dois ou vários participantes com usuários externos

## <a name="see-also"></a>Confira também
<a name="Types"> </a>

[Planejar clientes e dispositivos](../../SfbServer/plan-your-deployment/clients-and-devices/clients-and-devices.md)

[Atualizações mais recentes para versões do Skype for Business que usam o Windows Installer (MSI)](../../SfbServer/sfb-client-updates.md)
