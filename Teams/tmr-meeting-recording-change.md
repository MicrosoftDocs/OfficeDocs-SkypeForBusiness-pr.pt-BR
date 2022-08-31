---
title: Usar o OneDrive for Business e o SharePoint para gravações de reunião
author: CarolynRowe
ms.author: crowe
ms.reviewer: debhag
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Saiba como alternar do armazenamento de gravação de reunião do Stream para o OneDrive for Business e SharePoint no Microsoft Teams.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: e78cbb4740b5839af7c6c2d09450220a080d036f
ms.sourcegitcommit: 7a1fb6e15c21368afa34cd212865437781f721e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/31/2022
ms.locfileid: "67466110"
---
# <a name="use-onedrive-for-business-and-sharepoint-or-stream-for-meeting-recordings"></a>Usar o OneDrive for Business e o SharePoint ou o Stream para gravações de reunião

> [!NOTE]
> A alteração do armazenamento de gravações de reunião do Teams do Fluxo Clássico para o OneDrive e do SharePoint (ODSP) foi concluída a partir de 30 de agosto de 2021. Todas as gravações agora são armazenadas no ODSP. Essa alteração substitui a política RecordingStorageMode e a modificação da configuração no PowerShell não tem mais nenhum impacto.

|Data&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Evento&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;                                                                                                                                                                                                                                                                                                             |
|:-----------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|5 de outubro de 2020<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;| Você habilita a política de Reunião do Teams para que as gravações de reunião sejam salvas no OneDrive for Business e no SharePoint em vez de no Microsoft Stream (Clássico)|
|A implantação começa em 7 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|Todas as gravações de reunião do Teams serão salvas no OneDrive for Business e no SharePoint a menos que você atrase esta alteração ao modificar as políticas de Reunião do Teams da sua organização e configurá-las explicitamente para **Stream**. Ver o relatório de política como Stream não é suficiente. Você precisa definir explicitamente o valor da política para **Stream**.|
|A implantação começa em 11 de janeiro de 2021<br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC**<br> Embora os clientes GCC possam recusar a partir de 5 de outubro, você não pode aceitar. Este recurso será implantado para todos os clientes GCC a partir de 11 de janeiro de 2021, a menos que você tenha recusado.<br>  <br>A partir de 11 de janeiro de 2021, todas as gravações de reunião do Teams para clientes GCC serão salvas no OneDrive for Business e no SharePoint, a menos que você atrase essa alteração ao modificar as políticas de Reunião do Teams da sua organização e configurá-las explicitamente para **Stream**. <br><br>Se você recusou mas está pronto para ativar este recurso, pode fazê-lo configurando explicitamente a Política de Reunião do Teams para **OneDrive for Business**. |
|Em implantação a partir de 1 de março de 2021<br> *(Completo)*  &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Somente GCC alto e DoD**<br> Agora, os clientes podem habilitar gravações de reunião na nuvem em seus Microsoft Teams pela primeira vez. Essa gravações serão armazenadas e reproduzidas no OneDrive e no SharePoint por padrão. |
|Em implantação incremental a partir de 16 de agosto de 2021 <br> *(Completo)* &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;|**Todos os clientes (Enterprise, Education e GCC)**<br>As novas gravações de reunião não podem ser salvas no Microsoft Stream (Clássico); as gravações de reunião de todos os clientes serão salvas no OneDrive for Business e no SharePoint, mesmo se eles tiverem alterado as políticas de Reunião do Teams para Stream.<br><br> Recomendamos que os clientes, para controlar melhor a alteração na sua organização, aceitem quando estiverem confortáveis com a alteração em vez de esperar que ela aconteça. |

O Microsoft Teams tem um novo método para salvar gravações de reunião. Como a primeira fase de uma transição do Microsoft Stream clássico para o [novo Stream](/stream/streamnew/new-stream), esse método armazena gravações do Microsoft OneDrive for Business e do SharePoint no Microsoft 365 e oferece muitos benefícios.

> [!NOTE]
> Se uma gravação de reunião do Teams não for carregada com êxito no OneDrive/SharePoint, uma mensagem de erro "A gravação terminou inesperadamente" será exibida e a gravação será salva temporariamente nos Serviços de Mídia do Azure (AMS). Depois de armazenado no AMS, nenhuma tentativa de repetição é feita para carregar automaticamente a gravação no OneDrive/SharePoint ou stream.

As gravações de reuniões armazenadas no AMS ficam disponíveis por 21 dias antes de serem excluídas automaticamente. Os usuários podem baixar o vídeo do AMS se precisarem manter uma cópia.

Os benefícios do uso do OneDrive for Business e do SharePoint para armazenar gravações incluem:

- Políticas de retenção para gravação de reunião do Teams (TMR) (rótulos de retenção automática S+C E5)
- Desfrute da governança de informações do OneDrive for Business e do SharePoint
- Fácil de definir permissões e compartilhamento
- Compartilhar gravações com convidados somente com compartilhamento explícito
- Solicite o fluxo de acesso
- Forneça os links compartilhados do OneDrive for Business e do SharePoint
- As gravações de reunião ficam disponíveis mais rapidamente
- Suporte ao locatário do **Fique no Local** 
- Suporte Multi-Geo - As gravações são armazenadas em uma região específica para esse usuário
- Suporte ao Bring Your Own Key (BYOK)

Veja a lista completa de [recursos disponíveis hoje e o que esperar ao longo do tempo](/stream/streamnew/features-new-version-stream).

Veja "Novidades nas gravações de reuniões do Microsoft Teams" para obter mais informações.

> [!VIDEO https://www.youtube.com/embed/8iol0KfCeL8]

## <a name="set-up-the-meeting-recording-option-for-onedrive-for-business-and-sharepoint"></a>Configurar a opção de gravação de reuniões do OneDrive for Business e do SharePoint

A opção de gravação de reunião é uma configuração no nível de política do Teams. O exemplo a seguir mostra como definir a política Global. Certifique-se de que configurou a opção de gravação de reunião para a política ou políticas que atribuiu aos seus usuários.

> [!NOTE]
> As alterações na política de reunião do Teams levam algum tempo para serem propagadas. Verifique novamente após algumas horas após defini-la, saia e entre novamente no aplicativo Área de Trabalho do Teams ou simplesmente reinicie o computador.

1. Instale o Teams PowerShell.

   > [!NOTE]
   > O Conector Skype for Business Online atualmente faz parte do módulo mais recente do PowerShell do Teams. Se você estiver usando o último lançamento público do PowerShell Teams, não precisa instalar o Conector do Skype for Business Online. Confira [Gerenciar o Skype for Business Online com o PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell?preserve-view=true&view=o365-worldwide).

2. Abra o PowerShell como um administrador.

3. Instale o [módulo do PowerShell do Teams](./teams-powershell-install.md).

4. Importe o módulo do Microsoft Teams e entre como um administrador do Teams.

   ```powershell
   # When using Teams PowerShell Module
   
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

5. Use [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy) para definir uma Política de Reunião do Teams para fazer a transição do armazenamento do Stream para o do OneDrive for Business e do SharePoint. 

   ```powershell
   Set-CsTeamsMeetingPolicy -Identity Global -RecordingStorageMode "OneDriveForBusiness"
   ```

> [!NOTE]
> Se alguns dos seus usuários tiverem atribuído uma política por organizador ou por usuário, você deve definir esta configuração nesta política se quiser que eles também armazenem as gravações de reunião no OneDrive for Business e no SharePoint. Para mais informações, confira [Gerenciar políticas de reunião no Teams](meeting-policies-overview.md).

## <a name="permissions-or-role-based-access"></a>Permissões ou acesso baseado na função

> [!NOTE]
> Recomendamos que o destinatário seja um usuário conectado ao compartilhar gravações de reunião do Teams. Selecione a opção **Pessoas na (Sua Organização)** ao compartilhar o arquivo conforme documentado em [Compartilhar arquivos ou pastas do SharePoint](https://support.microsoft.com/office/1fe37332-0f9a-4719-970e-d2578da4941c). O compartilhamento externo não foi feito para distribuir arquivos grandes ou um número grande de arquivos.

|Tipo de reunião                               | Quem clicou em Gravar?| Para onde vai a gravação?                               |Quem tem acesso? De leitura/gravação, R ou compartilhamento                                                                                                                                                                                                                                                     |
|-------------------------------------------|-----------------------|--------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|Chamada privada com participantes internos             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem todos os direitos. <br /><br />O receptor (se estiver no mesmo locatário) tem acesso somente leitura. Sem acesso de compartilhamento. <br /><br /> O receptor da chamada (se estiver em outro locatário) não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com participantes internos             |Receptor da chamada                 |Conta do OneDrive for Business do receptor da chamada                        |O receptor da chamada é proprietário e tem todos os direitos. <br /><br />Chamador (se no mesmo locatário tiver acesso somente leitura. Sem acesso de compartilhamento. <br /><br />O chamador (se estiver em outro locatário) não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada privada com uma chamada externa             |Chamador                 |Conta do OneDrive for Business do chamador                        |O chamador é proprietário e tem todos os direitos.<br /> <br />O receptor da chamada não tem acesso. O chamador deve compartilhá-lo com o receptor da chamada.|
|Chamada privada com uma chamada externa             |Receptor da chamada                 |Conta do OneDrive for Business do receptor da chamada                        |O receptor da chamada é proprietário e tem todos os direitos.<br /><br />O chamador não tem acesso. O receptor da chamada deve compartilhá-lo com o chamador.|
|Chamada em grupo                                 |Qualquer membro da chamada |Membro do grupo que clicou na conta do OneDrive for Business da Gravação  |O membro que clicou em Gravar tem todos os direitos. <br /><br /> Outros membros do grupo do mesmo locatário têm direitos de leitura. <br /><br /> Os outros membros do grupo de locatários diferentes não têm direito à gravação.|
|Reunião agendada/adhoc                    |Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem todos os direitos à gravação. <br /><br /> Todos os outros membros da reunião têm acesso de leitura.|
|Reunião agendada/adhoc                    |Outro membro da reunião   |Membro da reunião que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. <br /><br />O organizador tem direitos de edição e pode compartilhar.<br /><br /> Todos os outros membros da reunião têm acesso de leitura.|
|Reunião ad hoc/agendada com participantes externos|Organizador              |Conta do OneDrive for Business do organizador                     |O organizador tem todos os direitos à gravação.<br /> <br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br /> Todos os outros participantes externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Reunião ad hoc/agendada com participantes externos|Outro membro da reunião   |Membro que clicou em Gravar                                  |O membro que clicou em Gravar tem todos os direitos à gravação. O organizador tem direitos de edição e pode compartilhar. <br /><br /> Todos os outros membros da reunião do mesmo locatário que o organizador têm acesso de leitura. <br /><br />Todos os outros participantes externos não têm acesso e o Organizador deve compartilhá-lo com eles.|
|Reunião de canal                            |Membro do canal         |Local do SharePoint do Teams para esse canal. **Observação**: não há suporte para carregamento de gravação de reunião de canal no SharePoint para restrições baseadas em IP. É recomendável usar [o acesso condicional do Azure](/azure/active-directory/conditional-access/overview). |O membro que clicou em Gravar tem direitos de edição à gravação. <br /> <br />As permissões dos outros membros são baseadas nas permissões do SharePoint do canal.|

## <a name="frequently-asked-questions"></a>Perguntas frequentes

**Onde a gravação será armazenada?**

- Para as reuniões que não forem de canal, a gravação será armazenada em uma pasta chamada **Gravações** que está no nível superior do OneDrive for Business que pertence à pessoa que iniciou a gravação da reunião. Exemplo:

  *Gravações do OneDrive for Business*/**do gravador**

- Para reuniões de canal, a gravação é armazenada na biblioteca de documentação de site do Teams em uma pasta chamada **Gravações**. Exemplo:

  *Nome do Teams - Nome do canal*/**Documentos**/**Gravações**

**Quando os arquivos do Stream (como gravações) são armazenados no SharePoint/OneDrive, como se decide para onde eles vão? O administrador tem a capacidade de alterar o destino?**

Por padrão, todos os arquivos de gravação irão para a conta do OneDrive do usuário que selecionou **Gravar**. Para reuniões de canal, a gravação sempre irá para o site do SharePoint do canal. O administrador não pode alterar o local de armazenamento da gravação.

**Como tratar das gravações de ex-funcionários?**

Como vídeos são como qualquer outro arquivo no OneDrive for Business e no SharePoint, o tratamento da propriedade e da retenção após a saída de um funcionário seguirá o [processo normal do OneDrive for Business e do SharePoint](/onedrive/retention-and-deletion).

**Quem tem as permissões para exibir a gravação da reunião?**

- Para reuniões que não são do canal, todos os convidados da reunião, exceto os participantes externos, receberão automaticamente um link compartilhado pessoalmente. Os participantes externos precisarão ser adicionados explicitamente à lista compartilhada pelo organizador da reunião ou pela pessoa que iniciou a gravação da reunião.

- Para as reuniões de canal, as permissões são herdadas da lista de proprietários e membros no canal.

> [!NOTE]
> Você não receberá um email quando a gravação terminar de salvar, mas a gravação aparecerá no chat da reunião quando terminar. Isso acontecerá muito mais rápido do que no Stream anteriormente.

**Como posso gerenciar as legendas?**

As legendas ocultas para gravações de reunião do Teams estarão disponíveis durante a reprodução somente se o usuário tiver ativado a transcrição no momento da gravação. Os administradores [devem ativar a transcrição de gravação](meetings-policies-recording-and-transcription.md#transcription) para garantir que seus usuários tenham a opção de gravar reuniões com transcrição.

As legendas ajudam a criar conteúdo inclusivo para visualizadores de todas as habilidades. Como proprietário, você pode ocultar legendas na gravação da reunião, embora a transcrição da reunião ainda esteja disponível no Teams, a menos que você a exclua lá.

As legendas ocultas têm suporte nas gravações de reunião do Teams por 60 dias a partir de quando a reunião foi gravada.

As legendas ocultas não terão suporte total se a Gravação de Reunião do Teams for movida ou copiada de seu local original no OneDrive for Business e no SharePoint.

> [!NOTE]
> Haverá legendas ocultas somente em inglês (a transcrição da reunião ainda não está disponível no GCC).

**Como minha cota de armazenamento será afetada?**

Os arquivos de gravação de reunião do Teams residem no OneDrive for Business e no SharePoint e estão incluídos na sua cota para esses serviços. Confira [cota do SharePoint](/sharepoint/sites/plan-site-maintenance-and-management#quotas) e [cota do OneDrive for Business](/onedrive/set-default-storage-space).

Você obtém mais armazenamento com o [OneDrive for Business](/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits) em comparação como o Stream e mais armazenamento fungível com o SharePoint.

**Como posso reproduzir uma gravação de reunião do Teams?**

Seu vídeo será reproduzido no reprodutor de vídeo do OneDrive for Business ou do SharePoint, dependendo de onde você acessar o arquivo.

**Se você planeja substituir a adição ao Stream, os vídeos existentes ficarão como estão e por quanto tempo?**

O Stream, como uma plataforma, não será substituído em breve. Os vídeos que residem atualmente no Stream continuarão lá até começarmos a migração. Na migração, esses vídeos serão migrados para o OneDrive for Business e para o SharePoint. Verifique [os detalhes da migração](/stream/streamnew/migration-details) para obter mais informações.

**Como fazer um rótulo de retenção às gravações de reunião do Microsoft Teams?**

Confira [Como aplicar automaticamente um rótulo de retenção](/microsoft-365/compliance/apply-retention-labels-automatically).

**Como atribuir políticas aos meus usuários no Microsoft Teams e quais políticas têm precedência?**

Confira [Qual política tem precedência?](./policy-assignment-overview.md#which-policy-takes-precedence).

**Para onde vai a gravação se o usuário não tiver OneDrive for Business sharepoint ou se a cota de armazenamento estiver cheia?**

A gravação chegará em nosso local de armazenamento temporário, onde será mantida por 21 dias. Durante esse tempo, o organizador deve baixar a gravação. Se não for baixado dentro de 21 dias, a gravação será excluída.
