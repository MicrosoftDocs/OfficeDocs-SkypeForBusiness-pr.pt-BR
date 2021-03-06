---
title: Usar o OneDrive for Business e o SharePoint para gravações de reuniões
author: cichur
ms.author: v-cichur
ms.reviewer: hao.moy
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do Stream para o OneDrive for Business e o armazenamento de gravação de reuniões do SharePoint no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d18f6b5ef5b4668324a68b4456cd3ad5aa4b7364
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507974"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar o OneDrive for Business e o SharePoint ou Stream para gravações de reunião

> [!Note]
> A alteração de usar o Microsoft Stream para o OneDrive for Business e o Microsoft SharePoint para gravações de reunião será uma abordagem em fases.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de outubro de 2020<br> <br>*(Concluído)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Você permite que a política de Reunião do Teams tenha gravações de reunião salvas no OneDrive for Business e no SharePoint em vez do Microsoft Stream (Clássico)|
|Implantando a partir de 7 de janeiro de 2021<br> <br>*(Concluído)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas as novas gravações de reunião do Teams serão salvas no OneDrive for Business e no SharePoint, a menos que você atrase essa alteração modificando as políticas de Reunião do Teams da sua organização e definindo-as explicitamente como **Stream**. Não basta ver o relatório de política como Stream. Você precisa definir explicitamente o valor da política como **Stream**.|
|Implantando a partir de 11 de janeiro de 2021<br> <br>*(Concluído)*&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC**<br> Embora os clientes do GCC possam optar por sair a partir de 5 de outubro, você não pode optar. Esse recurso será lançado para todos os clientes GCC a partir de 11 de janeiro de 2021, a menos que você tenha optado pela aceitação.<br>  <br>A partir de 11 de janeiro de 2021, todas as novas gravações de reunião do Teams para clientes GCC serão salvas no OneDrive for Business e no SharePoint, a menos que você atrase essa alteração modificando as políticas de Reunião do Teams da sua organização e definindo-as explicitamente como **Stream**. <br><br>Se você optou por desativar, mas está pronto para ativar esse recurso, você pode fazer isso definindo sua Política de Reunião do Teams explicitamente como **OneDrive for Business**. |
|Implantando a partir de 1º de março de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC-High e DoD**<br> Os clientes agora podem habilitar gravações de reuniões na nuvem em seus Microsoft Teams pela primeira vez. Essas gravações serão armazenadas e tocadas no OneDrive e no SharePoint por padrão. |
|Implantando incrementalmente a partir de 7 de julho de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br>Nenhuma nova gravação de reunião pode ser salva no **Microsoft Stream (Clássico);** todos os clientes terão automaticamente gravações de reunião salvas no OneDrive for Business e no SharePoint, mesmo que tenham alterado suas políticas de reunião do Teams para Stream .<br><br> Recomendamos que os clientes este recurso seja lançado antes dessa data para que eles possam controlar o tempo da versão. |

> [!Note]
> Recomendamos que os clientes Corporativos e Educacionais, para controlar melhor a mudança em sua organização, adoe-se sempre que você estiver confortável com a mudança em vez de esperar que isso aconteça.

O Microsoft Teams tem um novo método para salvar gravações de reuniões. Como a primeira fase de uma transição do Microsoft Stream clássico para o novo [Stream](https://docs.microsoft.com/stream/streamnew/new-stream), esse método armazena gravações no Microsoft OneDrive for Business e no SharePoint no Microsoft 365 e oferece muitos benefícios.

Os benefícios de usar o OneDrive for Business e o SharePoint para armazenar gravações incluem:

- Políticas de retenção para TMR (registro de reunião do Teams) (rótulos de autoretenção do S+C E5)
- Beneficiar-se da governança de informações do OneDrive for Business e do SharePoint
- Fácil definir permissões e compartilhamento
- Compartilhar gravações com convidados (usuários externos) somente com compartilhamento explícito
- Solicitar fluxo de acesso
- Fornecer links compartilhados do OneDrive for Business e do SharePoint
- As gravações de reunião estão disponíveis mais rapidamente
- **Ir suporte a** locatários locais
- Suporte multi-geo – as gravações são armazenadas em uma região específica desse usuário
- Traga seu próprio suporte de chave (BYOK)

Há algumas limitações a considerar:

- Haverá legendas fechadas somente em inglês e você poderá alternar legendas off/on.
- Inicialmente, *você* não poderá exibir, editar e pesquisar uma transcrição completa (no entanto, estamos trabalhando para adicionar esse recurso em breve).
- Você não poderá editar as transcrições, mas poderá alternar as legendas para fora/para cima.
- Você pode controlar com quem compartilhar a gravação, mas não poderá impedir que pessoas com acesso compartilhado baixem a gravação.
- Você não receberá um email quando a gravação terminar de salvar, mas a gravação aparecerá no chat da reunião depois que terminar. Isso acontecerá muito mais rápido do que no Stream anteriormente

Assista a "Gravação de Reunião" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar a opção de gravação de reunião para OneDrive for Business e SharePoint

A opção de gravação de reunião é uma configuração no nível de política do Teams. O exemplo a seguir mostra como definir a política Global. Certifique-se de definir a opção de gravação de reunião para a política ou políticas atribuídas aos usuários.

> [!Note]
> As alterações na política de reunião do Teams levam algum tempo para se propagar. Verifique novamente após algumas horas de defini-lo e, em seguida, saia e entre novamente.

1. Instale o PowerShell do Skype for Business Online.

   > [!NOTE]
   > O Skype for Business Online Connector atualmente faz parte do módulo mais recente do Teams PowerShell. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Conector do Skype for Business Online. Consulte [Gerenciar o Skype for Business Online com o PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    1. Baixe [o Skype for Business Online PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true).

    1. Siga os prompts para instalá-lo.

    1. Reinicie o computador.

2. Iniciar o PowerShell como administrador.

3. Importe o SkypeOnline Connector e entre como administrador do Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) para definir uma Política de Reunião do Teams para fazer a transição do armazenamento stream para o OneDrive for Business e o SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alguns de seus usuários tiver atribuído uma política por organizador ou por usuário, você deverá definir essa configuração nesta política se quiser que eles também armazenem as gravações de reunião no OneDrive for Business e no SharePoint. Para obter mais informações, consulte [Gerenciar políticas de reunião no Teams](meeting-policies-in-teams.md).

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Opt out of OneDrive for Business and SharePoint to continue using Stream

Mesmo que uma política diga que está definida como **Stream**, talvez ela não seja definida. Normalmente, se a política não estiver definida, a configuração padrão será **Stream**. No entanto, com essa nova alteração, se você quiser optar por não usar o SharePoint ou o OneDrive for Business, você deverá redefinir a política para **Stream** para garantir que **o Stream** seja o padrão.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permissões ou acesso baseado em função

> [!Note]
> Recomendamos que o destinatário seja necessário para ser um usuário conectado ao compartilhar Gravações de Reunião do Teams. Selecione a **opção Pessoas em (Sua Organização)** ao compartilhar o arquivo conforme documentado em arquivos [ou pastas do SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) O compartilhamento externo não foi projetado para a distribuição de arquivos grandes ou um grande número de arquivos. Para evitar cenários de fraude e abuso, você pode ter problemas ao compartilhar uma grande quantidade de dados para usuários externos.

|Tipo de reunião                               | Quem clicou em Record?| Onde a gravação chega?                               |Quem tem acesso? R/W, R ou compartilhamento                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|1:1 chamada com partes internas             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem direitos completos. <br /><br />O chamador (se estiver no mesmo locatário) tem acesso somente leitura. Sem acesso de compartilhamento. <br /><br /> O chamador (se em locatário diferente) não tiver acesso. O chamador deve compartilhá-lo com o Chamador.|
|1:1 chamada com partes internas             |Receptor                 |Conta do OneDrive for Business do destinatário                        |O chamador é proprietário e tem direitos completos. <br /><br />Chamador (se no mesmo locatário tiver acesso somente leitura. Sem acesso de compartilhamento. <br /><br />O chamador (se em locatário diferente) não tiver acesso. O chamador deve compartilhá-lo com o Chamador.|
|1:1 chamada com uma chamada externa             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem direitos completos.<br /> <br />O chamador não tem acesso. O chamador deve compartilhá-lo com o Chamador.|
|1:1 chamada com uma chamada externa             |Receptor                 |Conta do OneDrive for Business do destinatário                        |O chamador é proprietário e tem direitos completos.<br /><br />O chamador não tem acesso. O chamador deve compartilhá-lo com o Chamador.|
|Chamada de grupo                                 |Qualquer membro da chamada |Membro do grupo que clicou na conta do OneDrive for Business da Record  |O membro que clicou em Record tem direitos completos. <br /><br /> Outros fr do mesmo locatário têm direitos de leitura. <br /><br /> Outros membros do grupo de locatários diferentes não têm direitos sobre ele.|
|Adhoc/Reunião agendada                    |Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem direitos completos sobre a gravação. <br /><br /> Todos os outros membros da reunião têm acesso de leitura.|
|Adhoc/Reunião agendada                    |Outro membro da reunião   |Membro da reunião que clicou em Record                                  |O membro que clicou em Record tem direitos completos para a gravação. <br /><br />O organizador tem direitos de edição e pode compartilhar.<br /><br /> Todos os outros membros da reunião têm acesso de leitura.|
|Adhoc/Reunião agendada com usuários externos|Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem direitos completos sobre a gravação.<br /> <br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br /> Todos os outros membros externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Adhoc/Reunião agendada com usuários externos|Outro membro da reunião   |Membro que clicou em Record                                  |O membro que clicou em Record tem direitos completos para a gravação. O organizador tem direitos de edição e pode compartilhar. <br /><br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br />Todos os outros membros externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Reunião do canal                            |Membro do Canal         |Localização do SharePoint do Teams para esse canal                   |O membro que clicou em Record tem direitos de edição para a gravação. <br /> <br />As permissões de cada membro são baseadas nas permissões do SharePoint do Canal.|

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Onde a gravação da reunião será armazenada?**

- Para reuniões que não são do Canal, a gravação é armazenada em uma pasta chamada **Gravações** que está no nível superior do OneDrive for Business que pertence à pessoa que iniciou a gravação da reunião. Exemplo:

  <i>OneDrive for Business</i> / do gravador **Gravações**

- Para reuniões do Canal, a gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Recordings**. Exemplo:

  <i>Nome do Teams - Nome do canal</i> / **Documentos** / **Gravações**

**Quando os arquivos stream (como gravações) são armazenados no SharePoint/OneDrive, como é decidido para onde eles vão? O administrador tem a capacidade de mudar para onde vai?**

Por padrão, todos os arquivos de gravação serão para a conta do OneDrive do usuário que **selecionou Record**. Para reuniões de canal, a gravação sempre irá para o site do SharePoint do canal. O administrador não pode alterar onde a gravação está armazenada.

**Como lidar com gravações de antigos funcionários?**

Como os vídeos são como qualquer outro arquivo no OneDrive for Business e no SharePoint, lidar com a propriedade e a retenção depois que um funcionário sair seguirá o processo normal do OneDrive for Business e [do SharePoint.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Quem tem as permissões para exibir a gravação da reunião?**

- Para reuniões que não são do Canal, todos os convites de reunião, exceto para usuários externos, receberão automaticamente um link compartilhado pessoalmente. Os usuários externos precisarão ser adicionados explicitamente à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.

- Para reuniões do Canal, as permissões são herdadas dos proprietários e da lista de membros no canal.

**Como posso gerenciar transcrições?**

Os clientes que optarem por essa visualização não terão legendas fechadas disponíveis em suas Gravações de Reunião do Teams migradas para o OneDrive for Business e o SharePoint.Estamos trabalhando para adicionar legendas, começando com legendas fechadas em inglês, às gravações de reunião no Q4 CY2020.

As legendas fechadas estarão disponíveis em Gravações de Reunião do Teams para clientes que optaram por permitir transcrições conforme descrito em gravações na nuvem [do Teams.](cloud-recording.md)

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas, embora a transcrição ainda esteja disponível no Teams, a menos que exclua as legendas do Teams. Veja [como ativar ou desativar gravações de reunião.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

As legendas fechadas são suportadas para gravações de reunião do Teams por 60 dias a partir do momento em que a reunião é gravada.

As legendas fechadas não têm suporte total se a Gravação de Reunião do Teams for movida ou copiada de seu local original no OneDrive for Business ou no SharePoint.

**Como minha cota de armazenamento será impactada?**

Os arquivos de gravação de reunião do Teams ao vivo no OneDrive for Business e no SharePoint e estão incluídos em sua cota para esses serviços. Consulte [Cota do SharePoint e](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) cota do [OneDrive for Business.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Você obterá mais armazenamento com [o OneDrive for Business em](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) comparação com Stream e armazenamento mais divertido com o SharePoint.

**Como posso reproduzir uma gravação de reunião do Teams?**

Seu vídeo será reproduzido no player de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessa o arquivo.

**Se você planeja preteri-lo, os vídeos existentes permanecerão como estão e por quanto tempo?**

O fluxo como uma plataforma não será preterido em um futuro próximo. Os vídeos que atualmente vivem no Stream permanecerão lá até começarmos a migrar. Após a migração, esses vídeos também serão migrados para o OneDrive for Business ou para o SharePoint. Verifique [a migração clássica do Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) para obter mais informações.

**Como aplicar um rótulo de retenção?**

Consulte [Como aplicar automaticamente um rótulo de retenção.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Como atribuir políticas aos meus usuários no Microsoft Teams e quais políticas têm precedência?**

Veja [Qual política tem precedência?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
