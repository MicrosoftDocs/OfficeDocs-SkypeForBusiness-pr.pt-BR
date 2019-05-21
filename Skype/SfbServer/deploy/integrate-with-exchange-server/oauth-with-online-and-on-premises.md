---
title: Integração entre o Skype for Business Online e o Exchange Server
ms.reviewer: cbland
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 4/2/2019
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: ffe4c3ba-7bab-49f1-b229-5142a87f94e6
description: A configuração da autenticação OAuth entre o Exchange local e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em suporte a recursos.
ms.openlocfilehash: be1fd4ae0c1a1046a8da1d9a30550ac238a4034a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278123"
---
# <a name="configure-integration-between-skype-for-business-online-or-microsoft-teams-and-exchange-server"></a>Configurar a integração entre o Skype for Business online ou o Microsoft Teams e o Exchange Server 

A configuração da integração entre o Exchange Server e o Skype for Business Online permite que os recursos de integração do Skype for Business e do Exchange descritos em [suporte a recursos](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).

Este tópico se aplica à integração com o Exchange Server 2013 a 2019.

## <a name="what-do-you-need-to-know-before-you-begin"></a>O que você precisa saber antes de começar?

- Tempo estimado para concluir esta tarefa: 15 minutos

-  Você precisa receber permissões antes de realizar esse procedimento ou procedimentos. Para ver quais permissões você precisa, consulte o tópico [permissões de infraestrutura do Shell e do Exchange](https://go.microsoft.com/fwlink/p/?LinkId=746511) .

- Para obter informações sobre os atalhos de teclado que podem ser aplicáveis aos procedimentos deste tópico, consulte [atalhos de teclado no centro de administração do Exchange]( https://go.microsoft.com/fwlink/p/?LinkId=746512).

## <a name="configure-integration-between-exchange-server-and-o365"></a>Configurar a integração entre o Exchange Server e o O365

### <a name="step-1-configure-oauth-authentication-between-exchange-server-and-o365"></a>Etapa 1: configurar a autenticação OAuth entre o Exchange Server e o O365

Execute as etapas do seguinte artigo:

[Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)

### <a name="step-2-create-a-new-mail-user-account-for-the-skype-for-business-online-or-teams-partner-application"></a>Etapa 2: criar uma nova conta de usuário de email para o Skype for Business online ou o aplicativo para parceiros de equipe

Esta etapa é feita no Exchange Server. Ela criará um usuário de caixa de correio e atribuirá os direitos apropriados da função de gerenciamento. Essa conta será então usada na próxima etapa.

Especifique um domínio verificado para sua organização do Exchange. Esse domínio deve ser o mesmo usado como o domínio SMTP principal usado para as contas do Exchange no local. Esse domínio é chamado \<de domínio\> verificado no procedimento a seguir. Além disso, \<o\> DOMAINCONTROLLERFQDN deve ser o FQDN de um controlador de domínio.

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

### <a name="step-3-create-and-enable-a-partner-application-for-skype-for-business-online-or-teams"></a>Etapa 3: criar e habilitar um aplicativo parceiro para o Skype for Business online ou o Teams

Crie um novo aplicativo parceiro e use a conta que você acabou de criar. Execute o seguinte comando no PowerShell do Exchange em sua organização do Exchange local.

``` Powershell
New-PartnerApplication -Name SfBOnline -ApplicationIdentifier 00000004-0000-0ff1-ce00-000000000000 -Enabled $True -LinkedAccount $user.Identity
```

### <a name="verify-your-success"></a>Verifique se a operação foi realizada com sucesso

Verifique se a configuração está correta verificando se alguns dos recursos estão funcionando com êxito. 

1. Confirmar a delegação do calendário do Outlook funciona betweeen dois usuários do teams com as caixas de correio do Exchange Server 2016 ou do 2019.

2. Confirme se o histórico de conversas para clientes móveis está visível na pasta Histórico de conversas do Outlook.

Como alternativa, examine seu tráfego. O tráfego em um handshake OAuth é realmente distintivo (e não se parece com autenticação básica), especialmente em relação a territórios, onde você começará a ver o tráfego do emissor que tem a seguinte aparência: 00000004-0000-0ff1-ce00-000000000000 @ (às vezes com/antes o símbolo @), nos tokens que estão sendo passados. Você não verá um nome de usuário ou senha, que é o ponto de OAuth. Mas você verá o emissor "Office" – neste caso, ' 4 ' é o Skype for Business – e o território da sua assinatura.

Se você quiser ter certeza de que está usando o OAuth com êxito, verifique se sabe o que esperar e saiba para que tal tráfego deve ser exibido. Portanto, [Veja o que esperar](https://tools.ietf.org/html/draft-ietf-oauth-v2-23#page-34), aqui está um exemplo bem padrão [de tráfego OAuth em um aplicativo da Microsoft](https://download.microsoft.com/download/8/5/8/858F2155-D48D-4C68-9205-29460FD7698F/[MS-SPS2SAUTH].pdf) (muito útil para ler, embora não use tokens de atualização), e existem extensões Fiddler que permitem que você examine seu JWT OAuth (JSON Token da Web).

Veja um [exemplo de](https://blogs.msdn.microsoft.com/kaevans/2015/03/30/updated-fiddler-oauth-inspector/)como configurar um, mas você pode usar qualquer ferramenta de rastreamento de rede que você queira para empreender esse processo.

## <a name="related-topics"></a>Tópicos relacionados

[Configurar a autenticação OAuth entre organizações Exchange e Exchange Online](https://docs.microsoft.com/en-us/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)
