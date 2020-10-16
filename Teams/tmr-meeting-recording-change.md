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
ms.openlocfilehash: 624dcb4f99bc8ae2b83a1b8f62917ac0a5701888
ms.sourcegitcommit: 8a345ca9a8ddc6a84f9e270ab55f1b28f6ba49c8
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48486766"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reunião

> [!Note]
> A alteração do uso do Microsoft Stream para o OneDrive for Business e do Microsoft SharePoint para gravações de reunião será uma abordagem em fases.


|Data|Evento|
|---|-----------------|
|CY20 no início do quarto trimestre|**A gravação de reunião do teams no OneDrive for Business e no SharePoint está disponível para aceitação ou cancelamento.**<br> Os administradores de locatários podem optar ou recusar o OneDrive for Business e o SharePoint Configurando a política de equipe no PowerShell|
|Mid CY20 do quarto trimestre|**Gravação de reunião do teams no OneDrive for Business e no SharePoint definido como padrão para locatários que não são recusados**<br> Esse é o caminho recomendado para a maioria dos clientes|
|T1 CY21|**Salvar a gravação da reunião do teams no fluxo clássico não é mais permitido**<br>Todos os locatários salvarão o registro de reunião do teams no OneDrive for Business e no SharePoint|


O Microsoft Teams tem um novo método para salvar gravações na reunião. Como a primeira fase de uma transição do fluxo clássico da Microsoft para o [novo fluxo](https://docs.microsoft.com/stream/streamnew/new-stream), esse método armazena gravações no Microsoft onedrive e no SharePoint no Microsoft 365 e oferece muitos benefícios.

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

Mesmo se uma política disser que está definida como **Stream**, ela pode não ser definida. Geralmente, se a política não estiver definida, a configuração padrão será **Stream**. No entanto, com essa nova alteração, se você quiser optar por usar o SharePoint ou o OneDrive, será necessário redefinir a política para **transmitir** para garantir que seja o padrão.

```PowerShell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permissões ou acesso baseado na função


|Tipo de reunião                               | Quem clicou no registro?| Onde está a gravação?                               |Quem tem acesso? R/W, R ou compartilhamento                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1 chamada com partes internas             |Chamador                 |Conta do OneDrive for Business do chamador                        |-O chamador é proprietário, tem permissões completas-o recurso de chamada (se estiver no mesmo locatário) tem acesso somente leitura, sem acesso de compartilhamento-Calle (se estiver em um locatário diferente) não tem acesso. O chamador deve compartilhá-lo para o receptor|
|1:1 chamada com partes internas             |Receptor                 |Conta do OneDrive for Business do chamador                        |-O proprietário é proprietário, tem direitos totais-quem está no mesmo locatário tem acesso somente leitura, sem acesso de compartilhamento-o autor de chamadas (se estiver em um locatário diferente) não tem acesso. O chamado deve compartilhá-lo para o chamador|
|1:1 chamada com chamada externa             |Chamador                 |Conta do OneDrive for Business do chamador                        |-O chamador é proprietário, tem direitos totais-o Calle não tem acesso. O chamador deve compartilhá-lo para o receptor|
|1:1 chamada com chamada externa             |Receptor                 |Conta do OneDrive for Business do chamador                        |-O proprietário é proprietário, tem direitos totais – o autor de chamada não tem acesso. O chamado deve compartilhá-lo para o chamador|
|Chamada em grupo                                 |Qualquer membro da chamada |Membro que clicou na conta do OneDrive for Business do registro  |-O membro que clicou em registro tem direitos totais – outros membros do mesmo locatário têm direitos de leitura: outros membros para diferentes não têm direitos a ele.|
|Reunião adhoc/agendada                    |Organizador              |Conta do OneDrive for Business do organizador                     |-O organizador tem permissões completas para a gravação-todos os outros membros da reunião têm acesso de leitura|
|Reunião adhoc/agendada                    |Outro membro de reunião   |Membro que clicou em gravar                                  |-O membro que clicou em registro tem direitos totais ao organizador de gravação tem direitos de edição e pode compartilhar-todos os outros membros têm acesso de leitura|
|Reunião adhoc/agendada com usuários externos|Organizador              |Conta do OneDrive for Business do organizador                     |-O organizador tem permissões completas para a gravação-todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura-todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo para ele|
|Reunião adhoc/agendada com usuários externos|Outro membro de reunião   |Membro que clicou em gravar                                  |-O membro que clicou em registro tem direitos totais ao organizador de gravação tem direitos de edição e pode compartilhar todos os outros membros da reunião a partir do mesmo locatário que o organizador tem acesso de leitura-todos os outros membros externos não têm acesso e o organizador deve compartilhá-lo para ele|
|Reunião de canal                            |Membro do canal         |Local do SharePoint do teams para esse canal                   |-Membro que clicou em registro tem direitos de edição para a gravação-as permissões de cada membro são baseadas nas permissões do SharePoint do canal|


## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Onde a gravação da reunião será armazenada?**

- Para reuniões não relacionadas ao canal, a gravação é armazenada em uma pasta chamada **gravações** que está no nível superior do onedrive que pertence à pessoa que iniciou a gravação da reunião. Exemplo

  <i>onedrive for Business</i> / do gravador **Gravações**

- Para reuniões de canal, a gravação é armazenada na biblioteca de documentação do site do teams em uma pasta chamada **gravações**. Exemplo

  <i>Nome do Team-nome</i> / do canal **Documentos** / do **Gravações**

**Como faço para lidar com gravações de ex-funcionários?**

Como os vídeos são como qualquer outro arquivo no OneDrive e no SharePoint, a manipulação da posse e da retenção após a publicação de um funcionário acompanhará o processo normal do [onedrive e do SharePoint]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process).

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

**Se você planeja substituir a adição ao Stream, os vídeos existentes permanecerão como estão e por quanto tempo?**

O fluxo como uma plataforma não será preterido em breve. Os vídeos que residem atualmente no fluxo permanecerão lá até começarmos a migrar. Após a migração, esses vídeos também serão migrados para o ODSP. Confira [aqui](https://docs.microsoft.com/stream/streamnew/classic-migration) para obter mais informações.
