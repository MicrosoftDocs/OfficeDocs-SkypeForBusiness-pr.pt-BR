---
title: Usar o OneDrive e o SharePoint para gravações de reunião
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do fluxo para o armazenamento de gravação de reunião do SharePoint e do SharePoint para o OneDrive for Business no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d1072f86d019415dbc97d0507ff9d76b2cbdc6e6
ms.sourcegitcommit: 5c232ab2dfe4374ac69701241e55b05b8de8eb3e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2020
ms.locfileid: "48269635"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reunião

> [!Note]
> A mudança do Microsoft Stream para o OneDrive for Business e o Microsoft Office SharePoint Online para gravações de reunião será uma abordagem em fases. Na inicialização, os administradores de locatários podem escolher esta nova opção de fluxo de trabalho hoje e começará a ver gravações automáticas do OneDrive for Business e do SharePoint em outubro de 2020. Em novembro, você precisará se recusar se quiser continuar a usar o Stream, e algum tempo no início de 2021 exigiremos que todos os clientes usem o OneDrive for Business e o SharePoint para novas gravações de reunião.

O Microsoft Teams tem um novo método para salvar gravações na reunião. Como uma partida do Stream, o método usa o Microsoft OneDrive e o SharePoint no Microsoft 365 e oferece muitos benefícios.

As vantagens de usar o OneDrive for Business e o SharePoint para armazenar gravações incluem:

- Políticas de retenção para a gravação de reuniões do Team (TMR) (rótulos de autoretenção do S + C E5)
- Beneficie-se do OneDrive for Business e do controle de informações do SharePoint
- Permissões e compartilhamento fáceis de definir
- Compartilhe gravações com convidados (usuários externos) apenas com compartilhamento explícito
- Fluxo de solicitação de acesso
- Fornecer links compartilhados do OneDrive for Business e do SharePoint
- Maior cota
- As gravações de reunião estão disponíveis mais rapidamente
- Suporte do locatário local para o **go**
- Suporte a várias regiões – as gravações são armazenadas em uma região específica desse usuário
- Dê suporte a essa chave (BYOK)
- Qualidade de transcrição aprimorada e atribuição de alto-falante

Há algumas limitações a serem consideradas:

- Haverá legendas e transcrições ocultas somente em inglês.
- Você não poderá pesquisar transcrições ou conteúdo.
- Você não conseguirá editar as transcrições, mas poderá ativar/desativar legendas.
- Você pode controlar com quem compartilha a gravação, mas não poderá bloquear pessoas com acesso compartilhado para baixar a gravação.
- Você não receberá um email quando a gravação terminar de salvar, mas a gravação será exibida no chat de reunião quando ela terminar. Isso ocorrerá muito mais rapidamente do que no fluxo anteriormente

Assista à "gravação na reunião" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar a opção de gravação de reunião do OneDrive for Business e do SharePoint

1. Instale o console de administração do PowerShell do Skype for Business online.

    a. Baixe o [Skype for Business online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide).

    b. Siga os prompts para instalá-lo.

    c. Reinicie o computador.

2. Iniciar o PowerShell como administrador

3. Importe o conector SkypeOnline e faça logon como administrador do teams.

```PowerShell
  Import-Module SkypeOnlineConnector
  $sfbSession = New-CsOnlineSession
  Import-PSSession $sfbSession
```

4. Use [set-csteamsmeetingpolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy?view=skype-ps) para definir uma política de reunião do teams para fazer a transição do armazenamento de fluxo para ODSP.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
```

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Recusar o OneDrive for Business e o SharePoint para continuar usando o Stream

Mesmo que uma política diga que já está definida como **Stream**, ela pode não ser definida. Se for definido como Nothing, o padrão será Stream. Se desejar recusar, você **deve** redefinir a política para **transmitir** para garantir que o fluxo seja o padrão.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Onde a gravação da reunião será armazenada?**

- Para reuniões não relacionadas ao canal, a gravação é armazenada em uma pasta chamada. Gravações * * que está no nível superior do OneDrive que pertence à pessoa que iniciou a gravação da reunião. Exemplo

  <i>onedrive for Business</i> / do gravador **Gravações**

- Para reuniões de canal, a gravação é armazenada na biblioteca de documentação do site do teams em uma pasta chamada **gravações**. Exemplo

  <i>Nome do Team-nome</i> / do canal **Documentos** / do **Gravações**

**Quem tem as permissões para exibir a gravação da reunião?**

- Em reuniões não canalizadas, todos os convidados da reunião, exceto para usuários externos, receberão automaticamente um link compartilhado pessoalmente. Os usuários externos precisarão ser explicitamente adicionados à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.

- Para reuniões de canal, as permissões são herdadas da lista de proprietários e membros no canal.

**Como eu posso gerenciar transcrições?**

Os clientes que optarem por esta visualização não terão legendas ocultas disponíveis em suas gravações de reunião do teams migradas para o OneDrive e o SharePoint.Estamos trabalhando para adicionar legendas, começando com legendas ocultas em inglês, para fazer gravações em reuniões em outubro de 2020.

As legendas ocultas estarão disponíveis em gravações de reunião do teams para clientes que optaram por permitir transcrições, conforme descrito em [gravações na nuvem do teams](cloud-recording.md)

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas, embora a transcrição ainda esteja disponível no Teams, a menos que você exclua as legendas do teams. Veja [como ativar ou desativar gravações de reunião](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

As legendas ocultas são suportadas para gravações de reunião do Team por 60 dias a partir de quando a reunião é gravada.

**Como a minha cota de armazenamento será afetada**

A reunião de equipes que grava arquivos residem no OneDrive for Business e no SharePoint e está incluída na sua cota para esses serviços. Consulte [cota do SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [cota do onedrive for Business] ( https://docs.microsoft.com/onedrive/set-default-storage-space) .

**Como faço para reproduzir uma gravação de reunião do teams?**

Seu vídeo será reproduzido no player de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessar o arquivo.
