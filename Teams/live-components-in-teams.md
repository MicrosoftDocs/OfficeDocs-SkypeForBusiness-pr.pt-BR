---
title: Gerenciar componentes em tempo Teams
author: HowlinWolf-92
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
ms.openlocfilehash: 7c05888191c98e2b7fe11637ad8fe5ba8a8c1132
ms.sourcegitcommit: 2ce417430b2aac770997daaf5ef5d844aa97fd84
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/11/2021
ms.locfileid: "60911855"
---
# <a name="manage-live-components-in-teams"></a>Gerenciar componentes em tempo Teams

Os componentes ao Teams chat oferecem uma nova maneira de criar, criar e tomar decisões juntos. Envie um componente, como uma tabela, uma lista de tarefas ou um parágrafo, onde todos no chat podem editar em linha e ver alterações à medida que são feitas. Isso significa que você pode coletar ideias e comentários de sua equipe enquanto realiza menos reuniões e minimiza a necessidade de threads de chat longo.
> [!Note]
> Os componentes ao vivo são o primeiro recurso do [aplicativo Do Microsoft Loop](https://www.microsoft.com/en-us/microsoft-loop) a ser disponibilizado Teams. Observe que "Componentes ao vivo" serão renomeados como "Componentes do Loop" no início de 2022.

**Realizar tarefas mais rápidas juntos.** Origem de uma agenda, controle os itens de ação de um grupo ou tome anotações coletivamente. Esses são apenas alguns cenários mais fáceis com componentes ao vivo.

**Compartilhar componentes.** Nesta versão, você pode compartilhar componentes ao vivo em diferentes Teams chats. Os destinatários podem editar de onde quer que estejam e ver atualizações instantaneamente, independentemente de onde as alterações foram feitas. Em versões futuras, os componentes ao vivo terão suporte em Teams de reunião e canais, Outlook e, eventualmente, em todos os Microsoft 365 aplicativos.

**Comece no chat, crie a partir daí.** Todos os componentes que você cria Teams chat são salvos automaticamente em um arquivo em OneDrive. Portanto, você pode começar a colaborar no chat e depois mover para o arquivo, onde você tem um espaço visual maior para edição e pode adicionar quantos componentes quiser.

## <a name="clients-and-platforms"></a>Clientes e plataformas

Disponível em Teams aplicativos em Windows, Mac, Linux, iOS e Android.

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
PS C:\\WINDOWS\\system32&gt; set-SPOTenant -isFluidEnabled $true
PS C:\\WINDOWS\\system32&gt;
```
## <a name="known-issues"></a>Problemas conhecidos

- Os componentes ao vivo no chat não podem ser editados por Aplicativo do Office ao usar Teams no Android.

- Se as permissões de arquivo padrão do locatário são definidas como Pessoas específicas (somente as pessoas que o usuário **especifica)** e o remetente remove alguns usuários da lista Pessoas específicas na caixa de diálogo permissões ao criar um componente, esses usuários ainda podem ter acesso ao conteúdo. Esse problema ocorre devido à limitação de gerenciamento de acesso da caixa de diálogo de permissão e será corrigido na versão futura.

- Se as configurações da Política de Acesso Condicional do locatário impedirem que a rede cliente se conecte , os componentes ao vivo não funcionarão conforme o esperado para salvar alterações em tempo `https://pushchannel.1drv.ms` real no serviço.

## <a name="known-limitations"></a>Limitações conhecidas

- Pesquisar componentes ao vivo Teams pesquisa retornará um link para o componente no office.com, não a mensagem de chat em si.

- Os componentes ao vivo são desabilitados em chats federados.

- Os convidados B2B não poderão colaborar no componente ao vivo compartilhado com eles por meio do Company Share Link, a menos que o locatário desempate a opção de acesso externo para permitir que os convidados B2B tenham o mesmo nível de acesso que os membros do locatário.

- Teams O suporte completo do cliente Web de componentes Live estará disponível em breve.

- Os componentes ao vivo ainda não são suportados Teams canais, mas a edição em linha nos canais é planejada para mais experiências no futuro.

- Com as permissões de arquivo padrão do locatário definidas como Pessoas específicas (somente as pessoas que o usuário **especifica),** copiar o link para o componente ao vivo e colar em outro chat exige que o remetente use a caixa de diálogo permissões e adicione os destinatários na opção Pessoas específicas para conceder acesso corretamente.

- Com permissões de arquivo padrão de locatário definidas como Pessoas específicas (somente as pessoas que o usuário **especifica),** a criação de um componente ao vivo no chat em grupo com mais de 20 membros exigirá que o remetente selecione manualmente as opções de permissão para o componente.

- Os componentes ao vivo no chat não serão carregados somente se o arquivo tiver sido movido para uma biblioteca diferente. Se o arquivo for movido para uma pasta diferente, ele continuará a ser carregado no chat.

## <a name="how-to-check-your-tenants-default-file-permissions"></a>Como verificar as permissões de arquivo padrão do locatário

1. Vá para o [Centro de administração do Microsoft 365](https://admin.microsoft.com/).

2. À esquerda, em **Centros de administração,** selecione **SharePoint**.

3. Selecione   >  **Compartilhamento de** Políticas e, em Links de arquivo e **pasta,** exibir as permissões de arquivo padrão do locatário.

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
