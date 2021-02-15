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
description: Saiba como alternar do armazenamento de gravação de reuniões do Stream para o OneDrive for Business e do SharePoint no Microsoft Teams.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: c3172250c1bf6fe914c331712db74a83ebe98a6d
ms.sourcegitcommit: bfada4fd06c5cff12b0eefd3384bb3c10d10787f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/12/2021
ms.locfileid: "50196345"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reuniões

> [!Note]
> A mudança do uso do Microsoft Stream para o OneDrive for Business e o Microsoft SharePoint para gravações de reuniões será uma abordagem em fases.

|<div style="width:290px">Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;</div> |Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de outubro de 2020 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Você pode habilitar a política de Reunião do Teams para que as gravações de reuniões possam ser salvas no OneDrive for Business e no SharePoint em vez do Microsoft Stream (Clássico)|
|Sendo implantada a partir de 7 de janeiro de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas as novas gravações de reunião do Teams serão salvas no OneDrive for Business e no SharePoint, a menos que você atrase essa alteração modificando as políticas de Reunião do Teams da sua organização e definindo-as explicitamente para **o Stream.** Ver o relatório de política como Stream não é suficiente. Você precisa definir explicitamente o valor da política como **Stream.**|
|Sendo implantada a partir de 11 de janeiro de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC**<br> Embora os clientes do GCC possam optar por sair a partir de 5 de outubro, você não poderá optar. Esse recurso será lançado para todos os clientes GCC a partir de 11 de janeiro de 2021, a menos que você tenha optado por sair.<br>  <br>A partir de 11 de janeiro de 2021, todas as novas gravações de reuniões do Teams para clientes GCC serão salvas no OneDrive for Business e no SharePoint, a menos que você atrase essa alteração modificando as políticas de Reunião do Teams da sua organização e definindo-as explicitamente como **Stream.** <br><br>Se você optou por desativar, mas está pronto para ativar esse recurso, pode ser que isso seja feito configurando sua Política de Reunião do Teams explicitamente para **o OneDrive for Business.** |
|Sendo implantada a partir de 1º de março de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes & GCC corporativos**<br>Nenhuma nova gravação de reunião pode ser salva no **Microsoft Stream (Clássico);** todos os clientes terão automaticamente gravações de reunião salvas no OneDrive for Business e no SharePoint, mesmo que eles tenham alterado suas políticas de reunião do Teams para o Stream.<br><br> Recomendamos que os clientes versões desse recurso antes dessa data possam controlar o tempo do lançamento. |
|Lançado a partir de 7 de julho de 2021 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Clientes de educação**<br>Nenhuma nova gravação de reunião pode ser salva no **Microsoft Stream (Clássico);** todos os clientes terão automaticamente gravações de reunião salvas no OneDrive for Business e no SharePoint, mesmo que eles tenham alterado suas políticas de reunião do Teams para o Stream.<br><br> Recomendamos que os clientes versões desse recurso antes dessa data possam controlar o tempo do lançamento. Atualizamos esse cronograma para fornecer aos clientes de educação a capacidade de concluir os semestres em andamento. |

> [!Note]
> Recomendamos que os clientes corporativos e educacionais, para controlar melhor a mudança em sua organização, optem sempre que você estiver confortável com a mudança em vez de esperar que isso aconteça.

O Microsoft Teams tem um novo método para salvar gravações de reuniões. Como a primeira fase de uma transição do Microsoft Stream clássico para o novo [Stream,](https://docs.microsoft.com/stream/streamnew/new-stream)esse método armazena gravações no Microsoft OneDrive for Business e no SharePoint no Microsoft 365 e oferece muitos benefícios.

Os benefícios de usar o OneDrive for Business e o SharePoint para armazenar gravações incluem:

- Políticas de retenção para gravação de reunião do Teams (TMR) (rótulos de autorretenção S+C E5)
- Benefícios da governança de informações do OneDrive for Business e do SharePoint
- Fácil definir permissões e compartilhamento
- Compartilhar gravações com convidados (usuários externos) somente com compartilhamento explícito
- Solicitar fluxo de acesso
- Fornecer links compartilhados do OneDrive for Business e do SharePoint
- Aumento da cota
- As gravações de reunião estão disponíveis com mais rapidez
- **Ir para o suporte de** locatário local
- Suporte multi-geo – as gravações são armazenadas em uma região específica desse usuário
- Suporte para sua própria chave (BYOK)

Há algumas limitações a considerar:

- Haverá legendas somente em inglês e você poderá alternar/desligar as legendas.
- Inicialmente, *você* não poderá exibir, editar e pesquisar uma transcrição completa (no entanto, estamos trabalhando para adicionar esse recurso em breve).
- Você não poderá editar as transcrições, mas poderá alternar/desligar as legendas.
- Você pode controlar com quem compartilha a gravação, mas não poderá impedir que as pessoas com acesso compartilhado baixem a gravação.
- Você não receberá um email quando a gravação terminar de salvar, mas a gravação aparecerá no chat da reunião assim que terminar. Isso acontecerá muito mais rápido do que no Stream anteriormente

Assista a "Gravação de Reunião" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar a opção de gravação de reunião para o OneDrive for Business e o SharePoint

A opção de gravação de reunião é uma configuração no nível de política do Teams. O exemplo a seguir mostra como definir a política Global. Certifique-se de definir a opção de gravação de reunião para a política ou políticas atribuídas aos usuários.

> [!Note]
> As alterações na política de reunião do Teams levam algum tempo para se propagarem. Verifique novamente após algumas horas de configuração, saia e entre novamente.

1. Instale o PowerShell do Skype for Business Online.
**Observação:** atualmente, o Skype for Business Online Connector faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando a versão pública mais recente do Teams PowerShell, não será necessário instalar o Skype for Business Online Connector. Consulte [Gerenciar o Skype for Business Online com o PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    a. Baixe [o PowerShell do Skype for Business Online.](https://docs.microsoft.com/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?view=o365-worldwide&preserve-view=true)

    b. Siga as solicitações para instalá-lo.

    c. Reinicie o computador.

2. Iniciar o PowerShell como administrador

3. Importe o SkypeOnline Connector e entre como administrador do Teams.

   ```powershell
   Import-Module MicrosoftTeams
   $sfbSession = New-CsOnlineSession
   Import-PSSession $sfbSession
   ```

4. Use [Set-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy) para definir uma Política de Reunião do Teams para fazer a transição do armazenamento de stream para o OneDrive for Business e o SharePoint.

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!Note]
> Se alguns de seus usuários têm atribuído uma política por organizador ou por usuário, você deve definir essa configuração nessa política se quiser que eles também armazenem as gravações da reunião no OneDrive for Business e no SharePoint. Para obter mais informações, consulte [Gerenciar políticas de reunião no Teams.](meeting-policies-in-teams.md)

## <a name="opt-out-of-onedrive-for-business-and-sharepoint-to-continue-using-stream"></a>Opte por sair do OneDrive for Business e do SharePoint para continuar usando o Stream

Mesmo que uma política diga que está definida como **Stream,** talvez ela não seja definida. Normalmente, se a política não estiver definida, a configuração padrão será **Stream.** No entanto, com essa nova alteração, se quiser optar por não usar o SharePoint ou o OneDrive for Business, você deverá redefinir a política para o **Stream** para garantir que **o Stream** seja o padrão.

```PowerShell
Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "Stream"
```

## <a name="permissions-or-role-based-access"></a>Permissões ou acesso baseado em função

> [!Note]
> Recomendamos que o destinatário seja um usuário conectado ao compartilhar Gravações de Reunião do Teams. Selecione a **opção Pessoas em (Sua Organização)** quando você compartilhar o arquivo como documentado em arquivos [ou pastas do SharePoint.](https://support.microsoft.com/office/share-sharepoint-files-or-folders-1fe37332-0f9a-4719-970e-d2578da4941c?redirectSourcePath=%25252fen-US%25252farticle%25252fShare-sites-or-documents-with-people-outside-your-organization-80E49744-E30F-44DB-8D51-16661B1D4232&ui=en-US&rs=en-US&ad=US) O compartilhamento externo não foi projetado para a distribuição de arquivos grandes ou um grande número de arquivos. Para evitar cenários de fraude e abuso, você pode ter problemas ao compartilhar uma grande quantidade de dados para usuários externos.

|Tipo de reunião                               | Quem clicou em Gravar?| Onde a gravação chega?                               |Quem tem acesso? R/W, R ou compartilhamento                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chamada 1:1 com partes internas             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem direitos completos. <br /><br />O destinatário da chamada (se estiver no mesmo locatário) tem acesso somente leitura. Sem acesso de compartilhamento. <br /><br /> O destinatário da chamada (se estiver em locatário diferente) não tem acesso. O chamador deve compartilhá-lo com o Destinatário da Chamada.|
|Chamada 1:1 com partes internas             |Receptor                 |Conta do OneDrive for Business do destinatário                        |O destinatário da chamada é proprietário e tem direitos completos. <br /><br />Chamador (se no mesmo locatário tiver acesso somente leitura. Sem acesso de compartilhamento. <br /><br />O chamador (se estiver em locatário diferente) não tem acesso. O destinatário da chamada deve compartilhá-lo com o Chamador.|
|Chamada 1:1 com uma chamada externa             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem direitos completos.<br /> <br />O destinatário da chamada não tem acesso. O chamador deve compartilhá-lo com o Destinatário da Chamada.|
|Chamada 1:1 com uma chamada externa             |Receptor                 |Conta do OneDrive for Business do destinatário                        |O destinatário da chamada é proprietário e tem direitos completos.<br /><br />O chamador não tem acesso. O destinatário da chamada deve compartilhá-lo com o Chamador.|
|Chamada em grupo                                 |Qualquer membro da chamada |Membro que clicou na conta do OneDrive for Business da Record  |O membro que clicou em Registro tem direitos completos. <br /><br /> Outros membros do mesmo locatário têm direitos de leitura. <br /><br /> Outros membros de locatários diferentes não têm direitos sobre ele.|
|Adhoc/Reunião agendada                    |Organizador              |Conta do Organizador do OneDrive for Business                     |O organizador tem direitos completos sobre a gravação. <br /><br /> Todos os outros membros da reunião têm acesso de leitura.|
|Adhoc/Reunião agendada                    |Outro membro da reunião   |Membro que clicou em Gravar                                  |O membro que clicou na Gravação tem direitos completos sobre a gravação. <br /><br />O organizador tem direitos de edição e pode compartilhar.<br /><br /> Todos os outros membros têm acesso de leitura.|
|Adhoc/Reunião agendada com usuários externos|Organizador              |Conta do Organizador do OneDrive for Business                     |O organizador tem direitos completos sobre a gravação.<br /> <br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br /> Todos os outros membros externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Adhoc/Reunião agendada com usuários externos|Outro membro da reunião   |Membro que clicou em Gravar                                  |O membro que clicou na Gravação tem direitos completos sobre a gravação. O organizador tem direitos de edição e pode compartilhar. <br /><br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br />Todos os outros membros externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Reunião de canal                            |Membro do Canal         |Localização do SharePoint do Teams para esse canal                   |O membro que clicou em Gravar tem direitos de edição para a gravação. <br /> <br />As permissões de todos os outros membros são baseadas nas permissões do SharePoint do Canal.|

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Onde a gravação da reunião será armazenada?**

- Para reuniões que não são do Canal,  a gravação é armazenada em uma pasta chamada Gravações que está no nível superior do OneDrive for Business que pertence à pessoa que iniciou a gravação da reunião. Exemplo:

  <i>OneDrive for Business do gravador</i> / **Gravações**

- Para reuniões do Canal, a gravação é armazenada na biblioteca de documentação do site do Teams em uma pasta chamada **Gravações.** Exemplo:

  <i>Nome do Teams - Nome do canal</i> / **Documentos** / **Gravações**

**Quando arquivos do Stream (como gravações) são armazenados no SharePoint/OneDrive, como é decidido para onde eles vão? O administrador tem a capacidade de alterar para onde vai?**

Por padrão, todos os arquivos de gravação irão para a conta do OneDrive do usuário que **selecionou Registro.** Para reuniões de canal, a gravação sempre irá para o site do SharePoint do canal. O administrador não pode alterar onde a gravação está armazenada.

**Como faço para lidar com gravações de ex-funcionários?**

Como os vídeos são como qualquer outro arquivo no OneDrive for Business e no SharePoint, lidar com a propriedade e a retenção depois que um funcionário sair seguirá o processo normal do OneDrive for Business e [do SharePoint.]( https://docs.microsoft.com/onedrive/retention-and-deletion#the-onedrive-deletion-process)

**Quem tem as permissões para exibir a gravação da reunião?**

- Para reuniões que não são do Canal, todos os convidados da reunião, exceto usuários externos, receberão automaticamente um link compartilhado. Os usuários externos precisarão ser explicitamente adicionados à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.

- Para reuniões do Canal, as permissões são herdadas dos proprietários e da lista de membros no canal.

**Como posso gerenciar transcrições?**

Os clientes que optarem por essa visualização não terão legendas fechadas disponíveis em suas Gravações de Reunião do Teams migradas para o OneDrive for Business e o SharePoint.Estamos trabalhando para adicionar legendas, começando com legendas fechadas em inglês, às gravações de reuniões no Q4 CY2020.

As legendas fechadas estarão disponíveis nas Gravações de Reunião do Teams para clientes que optaram por permitir transcrições conforme descrito nas gravações na nuvem [do Teams.](cloud-recording.md)

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas, embora a transcrição ainda esteja disponível no Teams, a menos que você exclua as legendas do Teams. Veja [como ativar ou desativar gravações de reunião.](cloud-recording.md#set-up-teams-cloud-meeting-recording-for-users-in-your-organization)

As legendas fechadas são suportadas para gravações de reuniões do Teams por 60 dias a partir de quando a reunião é gravada.

As legendas fechadas não têm suporte total se a Gravação de Reunião do Teams for movida ou copiada de seu local original no OneDrive for Business ou no SharePoint.

**Como minha cota de armazenamento será impactada?**

As reuniões do Teams gravam arquivos ao vivo no OneDrive for Business e no SharePoint e são incluídas em sua cota para esses serviços. Veja [a cota do SharePoint](https://docs.microsoft.com/sharepoint/sites/plan-site-maintenance-and-management#quotas) e a cota do [OneDrive for Business.](https://docs.microsoft.com/onedrive/set-default-storage-space)

Você obterá mais armazenamento com [o OneDrive for Business em](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) comparação com o Stream e um armazenamento mais fungível com o SharePoint.

**Como posso reproduzir uma gravação de reunião do Teams?**

Seu vídeo será reproduzido no player de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessar o arquivo.

**Se você planeja preteri-lo, os vídeos existentes permanecerão como estão e por quanto tempo?**

O stream como uma plataforma não será preterido em um futuro próximo. Os vídeos que atualmente vivem no Stream permanecerão lá até iniciarmos a migração. Após a migração, esses vídeos também serão migrados para o OneDrive for Business ou o SharePoint. Verifique [a migração clássica do Stream](https://docs.microsoft.com/stream/streamnew/classic-migration) para obter mais informações.

**Como aplicar um rótulo de retenção?**

Veja [como aplicar automaticamente um rótulo de retenção.](https://docs.microsoft.com/microsoft-365/compliance/apply-retention-labels-automatically?view=o365-worldwide#microsoft-teams-meeting-recordings)

**Como faço para atribuir políticas aos meus usuários no Microsoft Teams e quais políticas têm precedência?**

Veja [qual política tem precedência?](https://docs.microsoft.com/MicrosoftTeams/assign-policies#which-policy-takes-precedence).
