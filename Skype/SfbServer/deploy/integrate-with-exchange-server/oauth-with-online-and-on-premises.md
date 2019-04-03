---
title: Integração entre o Skype para Business Online e Exchange server
ms.reviewer: cbland
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/2/2019
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: Configurando o OAuth a autenticação entre o Exchange no local e Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos no suporte ao recurso.
ms.openlocfilehash: 976aae8287c1d9f209975d53ebc64ac80033c591
ms.sourcegitcommit: 42666cf15b37279244d205715016a10e01fc752e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/02/2019
ms.locfileid: "31040013"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configure a integração entre o Skype para negócios on-line ou equipes da Microsoft e o Exchange Server 

Configurando a integração entre o Exchange server e do Skype para Business Online permite que o Skype para recursos de integração do Exchange e de negócios descritos em [suporte de recurso](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tópico se aplica a integração com o Exchange Server 2013 por meio de 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para concluir esta tarefa: 15 minutos

-  Você precisa receber permissões antes de realizar esse procedimento ou procedimentos. Para ver quais permissões você precisa, consulte o tópico [Exchange and Shell infrastructure permissions](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obter informações sobre atalhos de teclado que possam se aplicar aos procedimentos neste tópico, consulte [atalhos de teclado no Centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configure a integração entre o Exchange Server e do O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Etapa 1: Configurar a autenticação OAuth entre o Exchange Server e do O365

Execute as etapas no seguinte artigo:

[Configurar a autenticação OAuth entre organizações do Exchange e o Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Etapa 2: Criar uma nova conta de usuário de email para o Skype para Business Online ou aplicativo de parceiro de equipes

Esta etapa é realizada no servidor Exchange. Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento. Essa conta será então usada na próxima etapa.

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo usado como o domínio SMTP primário usado para as contas do Exchange local. Este domínio é conhecido como \<seu domínio verificado\> no procedimento a seguir. Além disso, o \<DomainControllerFQDN\> deve ser o FQDN de um controlador de domínio.

``` Powershell
$user = New-MailUser -Name O365-ApplicationAccount -ExternalEmailAddress O365-ApplicationAccount@<your Verified Domain> -DomainController <DomainControllerFQDN>
```

Esse comando ocultará o novo usuário da caixa de correio das listas de endereços.

``` Powershell
Set-MailUser -Identity $user.Identity -HiddenFromAddressListsEnabled $True -DomainController <DomainControllerFQDN>
```

Esses dois próximos comandos atribuirão a função de gerenciamento de UserApplication e ArchiveApplication a esta nova conta.

``` Powershell
New-ManagementRoleAssignment -Role UserApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

``` Powershell
New-ManagementRoleAssignment -Role ArchiveApplication -User $user.Identity -DomainController <DomainControllerFQDN>
```

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Etapa 3: Criar e habilitar um aplicativo de parceiro do Skype para Business Online ou equipes

Crie um novo aplicativo parceiro e use a conta que você acabou de criar. Execute o seguinte comando no Exchange PowerShell em seu local de organização do Exchange.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Verifique se a operação foi realizada com sucesso

Verifique se a configuração está correta verificando que alguns dos recursos estão funcionando com êxito. 

1. Confirme se dois usuários de equipes betweeen com Exchange Server 2016 ou caixas de correio 2019 a delegação de calendário do Outlook funciona.

2. Confirme histórico da conversa para clientes móveis é visível na pasta Histórico da conversa do Outlook.

Como alternativa, examine o tráfego. O tráfego em um handshake OAuth é realmente característica (e não se parece com a autenticação básica), especialmente ao redor territórios, onde você vai começar a ver o tráfego de emissor parecida com esta: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com uma / antes o sinal @), em que estão sendo passados tokens. Você não verá um nome de usuário ou senha, que é o ponto do OAuth. Mas você verá o emissor 'Temporária' – nesse caso, '4' é Skype para negócios – e o território de sua assinatura.

Se você quiser ter certeza de que você estiver usando o OAuth com êxito, certifique-se de que você sabe o que esperar e quando já souber o que o tráfego deve se parecer com. Caso [aqui está o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um bem standard [exemplo de tráfego de OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (realmente úteis para mensagens lidas, embora não use Refresh tokens) e existem extensões Fiddler que permitirá que você procure em seu OAuth JWT (JSON Token de Web).

Aqui está um [exemplo de configuração de um](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/), mas você pode usar qualquer ferramenta de rastreamento de rede que você deseja realizar esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações do Exchange e o Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
