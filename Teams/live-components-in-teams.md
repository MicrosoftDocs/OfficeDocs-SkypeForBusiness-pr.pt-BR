---
title: Gerenciar componentes em tempo Teams
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: michalbr
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
description: Saiba como gerenciar componentes ao vivo em Teams.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: b8bda034030f2ccb6e12e23908f16ca212f4add0
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60750330"
---
# <a name="manage-live-components-in-teams"></a>Gerenciar componentes em tempo Teams

Os componentes ao Teams chat oferecem uma nova maneira de criar, criar e tomar decisões juntos. Envie um componente, como uma tabela, uma lista de tarefas ou um parágrafo, onde todos no chat podem editar em linha e ver alterações à medida que são feitas. Isso significa que você pode coletar ideias e comentários de sua equipe enquanto realiza menos reuniões e minimiza a necessidade de threads de chat longo.

**Realizar tarefas mais rápidas juntos.** Origem de uma agenda, controle os itens de ação de um grupo ou tome anotações coletivamente. Esses são apenas alguns cenários mais fáceis com componentes ao vivo.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes ao vivo em diferentes Teams chats. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas. Em versões futuras, os componentes ao vivo terão suporte em Teams de reunião e canais, Outlook e, eventualmente, em todos os Microsoft 365 aplicativos.

**Comece no chat, crie a partir daí.** Todos os componentes que você cria Teams chat são salvos automaticamente em um arquivo em OneDrive. Portanto, você pode começar a colaborar no chat e depois mover para o arquivo, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes quiser.

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em Teams aplicativos em Windows, Mac, Linux, iOS e Android.

A partir do início de setembro, os componentes ao vivo estarão disponíveis globalmente. No final de setembro, ele estará disponível para Nuvem da Comunidade Governamental Mod (GCC).

## <a name="settings-management"></a>Configurações gerenciamento

Os componentes live são construídos com Microsoft Fluid Framework com suporte no Microsoft 365 e controlados do SharePoint Online e não do centro de administração Teams do Teams.

Você precisará da versão mais recente do módulo SharePoint [PowerShell Online](/office365/enterprise/powershell/manage-sharepoint-online-with-office-365-powershell) para habilitar ou desabilitar todas as Experiências Fluidas em seu Office 365 locatário. Microsoft Fluid Framework padrão para **ON para** todos os locatários de versão direcionada. Como os componentes ao vivo são projetados para colaboração, os componentes são sempre compartilhados como editáveis por outras pessoas, mesmo que seu locatário seja definido como padrão para exibição somente para outros tipos de arquivo. Consulte o link **Saiba mais** ao lado da configuração para obter mais detalhes.

## <a name="checking-if-the-fluid-framework-is-enabled-through-the-sharepoint-online-powershell-cmdlet"></a>Verificar se a Fluid Framework está habilitada por meio do cmdlet SharePoint PowerShell Online

1. [Conexão para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Verifique se Fluid Framework está habilitado executando o cmdlet Get-SPOTenant sem argumentos.

3. Verifique se o valor de IsFluidEnabled é **verdadeiro**.

## <a name="enabling-the-fluid-framework-through-the-sharepoint-online-powershell-cmdlet"></a>Habilitando o Fluid Framework por meio do cmdlet SharePoint PowerShell Online 

1. [Conexão para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps#to-connect-with-a-user-name-and-password) 

2. Habilitar Fluido usando o cmdlet Set-SPOTenant -IsFluidEnabled $true 
   
   A alteração levará pouco tempo para ser aplicada em sua área de trabalho. 

O recurso estará disponível em Teams Windows Desktop, Mac, iOS, Android. Quando habilitado, os usuários verão uma nova opção para inserir componentes ao vivo na experiência de composição de mensagens para esses clientes.

## <a name="disabling-fluid-framework-through-sharepoint-online-powershell-cmdlet"></a>Desabilitando o Fluid Framework por meio SharePoint Cmdlet do PowerShell Online

1. [Conexão para SharePoint PowerShell Online.](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)

2. Desabilitar Fluido usando o cmdlet Set-SPOTenant Set-SPOTenant -IsFluidEnabled $false. 

   A alteração levará pouco tempo para ser aplicada em sua área de trabalho. 

Se você precisar reabilitar esse recurso, poderá usar SharePoint Cmdlets do PowerShell Online.

```powershell
C:\\WINDOWS\\system32&gt; Connect-SPOService
cmdlet Connect-SPOService at command pipeline position 1

Supply values for the following parameters:
Url: <https://a830edad9050849822e21011208-admin.sharepoint.com/>
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $false
PS C:\\WINDOWS\\system32&gt;
```

## <a name="known-limitations"></a>Limitações conhecidas

- Criar uma tabela ou uma lista de tarefas como o primeiro componente depois que o aplicativo Teams é reiniciado pode demorar um pouco mais.

- Outros membros do chat receberão uma notificação de email quando mencionado com um símbolo at (@). (As notificações de at-mentions no feed Teams atividade estarão disponíveis em breve.)

- Pesquisar componentes ao vivo dentro Teams pesquisa retornará um link para o componente no office.com, não a mensagem de chat em si.

- Os componentes ao vivo são desabilitados em chats federados e habilitados para chats regulares com uma conta de convidado usando o Azure B2B.

- Embora você possa compartilhar um componente em Teams canais e outros aplicativos Microsoft 365, os destinatários obterão um link na maioria dos locais no momento. A edição em linha é planejada para mais experiências no futuro.

## <a name="storage-of-fluid-files"></a>Armazenamento de `.fluid` arquivos

**Como `.fluid` são armazenados?**

Os componentes ao vivo criados Teams são respaldados por um arquivo armazenado no `.fluid` OneDrive for Business. Ser um arquivo no OneDrive for Business significa que os usuários podem criar, descobrir e gerenciar componentes ao vivo (arquivos) tão facilmente quanto qualquer documento `.fluid` Office.

Os usuários podem pesquisar conteúdo `.fluid` em arquivos Office.com e OneDrive for Business.
`.fluid` os arquivos funcionam com recursos de governança de dados, como Descoberta eDiscovery, auditoria, relatórios e ressarcimento legal.

`.fluid`os arquivos agora serão exibidos em Office.com e OneDrive for Business, como nas áreas Recente e Recomendada.
`.fluid`os arquivos podem ser restaurados para versões anteriores OneDrive for Business.

Os participantes do chat devem ter uma OneDrive para criar componentes ao vivo. Sem uma conta OneDrive, os participantes de chat ainda poderão colaborar em um componente criado por outros usuários que tenham uma conta OneDrive válida, mas não podem criar suas próprias.

[Mover](https://support.microsoft.com/en-us/office/move-files-and-folders-between-onedrive-and-sharepoint-5916f90d-f58a-4bf9-b135-10853f516d0b) um arquivo de OneDrive para um site de SharePoint resultará em falha na carga do componente ao vivo `.fluid` no Teams chat.

**O que acontece se o proprietário do arquivo sair da empresa?**

[OneDrive de retenção se](/microsoft-365/compliance/retention-policies-sharepoint?view=o365-worldwide#when-a-user-leaves-the-organization) aplicam aos arquivos da mesma forma `.fluid` que fazem com outros conteúdos criados pelo usuário.

**Como os `.fluid` arquivos são compartilhados?**

Os componentes ao vivo podem ser inseridos Teams chat ou copiados de um chat para outro. (Os componentes ao vivo ainda não têm suporte em canais.) Eles são padrão para as permissões existentes do locatário, mas os usuários podem alterar as permissões antes de enviar para garantir que todos tenham acesso.

Abrir componentes Teams chat no Office.com oferece funcionalidade de compartilhamento na parte superior da janela, semelhante às opções de compartilhamento oferecidas para outros documentos Office.

**E se um `.fluid` arquivo ficar corrompido ou danificado?**

Histórico de versão permite que você revise e copie de versões anteriores do arquivo.

**Quais aplicativos podem abrir e editar `.fluid` arquivos?**

`.fluid`os arquivos só podem ser abertos como links no navegador, como Office.com e como componentes ao vivo no Teams chat. Se baixados, eles não poderão ser abertos novamente sem primeiro enviá-los de volta para o OneDrive for Business ou SharePoint Online.
