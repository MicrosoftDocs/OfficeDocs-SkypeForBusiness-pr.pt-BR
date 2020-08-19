---
title: Planejando a desativação de métodos de autenticação herdados interna e externamente em sua rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Este artigo descreve os cmdlets que dão aos administradores mais controle dos métodos de autenticação usados dentro e fora de uma empresa. Os administradores podem ativar ou desativar os métodos de autenticação interna ou externamente em sua rede.
ms.openlocfilehash: e2f9a8c9c8576c07de3158fb2446cb3cb89bac72
ms.sourcegitcommit: aae3eeb4dedd825ab176abe7e1aff9463c88799b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/18/2020
ms.locfileid: "46797449"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planejar a desativação de métodos de autenticação herdados interna e externamente em sua rede.

> [!NOTE]
> Se você estiver prestes a ler este artigo, já deve conhecer as topologias de autenticação modernas, ADAL e sobre a configuração de autenticação moderna, mas, caso contrário, os artigos necessários para começar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
A autenticação moderna não só permite o uso de métodos mais seguros de autenticação, como autenticação de dois fatores, ou autenticação baseada em certificado, ela pode executar a autorização do usuário sem precisar de um nome de usuário ou senha. É muito útil.

Este artigo ajudará você a conectar brechas que foram exploradas por ataques de negação de serviço (DOS) nos servidores do Skype for Business, desativando os métodos mais antigos usados para autenticação, externamente, interna ou ambas, à sua rede. Por exemplo, um bom método para ajudar a evitar ataques de DOS seria desativar a autenticação integrada do Windows (que inclui NTLM e Kerberos). Desativar o NTLM externamente e confiar na autenticação baseada em certificado ajuda a proteger as senhas contra exposição. Isso ocorre porque o NTLM usa credenciais de senha para autenticar usuários, mas a autenticação baseada em certificado, habilitada pela autenticação moderna – não. Isso significa que uma opção ideal para reduzir ataques de DOS é bloquear o NTLM externamente e, em vez disso, usar apenas a autenticação baseada em certificado.

Tudo certo, vamos começar.

## <a name="what-would-you-be-changing"></a>O que você mudaria? 

Esses cmdlets funcionam para SIP e pontos de serviço Web do Access. Embora esses dois canais usem métodos de acesso diferentes, executando a gama de NTLM e Kerberos para acesso anônimo, todos os métodos padrão usados pelo Skype for Business foram levados em consideração.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Como obter os cmdlets Get-e Set-CsAuthConfig

Esses cmdlets serão instalados apenas após a atualização cumulativa de julho de 2018 (6.0.9319.534) para o Microsoft Skype for Business Server 2015, e você terá uma variedade de topologias que podem ser implantadas para o Skype for Business Server.

## <a name="topologies"></a>Topologias

É importante ter em mente que essas são as topologias com suporte envolvidas neste cenário! Se você precisar acessar o suporte para obter ajuda com o bloqueio de um método, por exemplo, será necessário ter uma configuração entre os tipos abaixo. 

> [!IMPORTANT]
> Na tabela e nas descrições abaixo, a *autenticação moderna* é abreviada como __ma__ e a *autenticação integrada do Windows* é abreviada como __Win__. Como um lembrete, a autenticação integrada do Windows é composta de dois métodos: autenticação NTLM e Kerberos. Você precisará saber isso para ler a tabela corretamente!


|       |Externamente  |Internos  |Parâmetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Ganho        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Ganho        | BlockModernAuthInternally         |

__Descrição do tipo 1:__ Este é o cenário padrão quando o MA é __ativado para o__ Skype for Business Server. Em outras palavras, este é o *ponto de partida* quando o Ma é configurado.

__Descrição do tipo 2:__ Essa topologia bloqueia NTLM *externamente*, mas permite que NTLM ou Kerberos (para clientes que não oferecem suporte a Adal) funcionem *internamente*. Se os seus clientes suportarem a ADAL, eles usarão o MA internamente.

__Descrição do tipo 3:__ Essa topologia requer MA para todos os usuários. Todos os clientes compatíveis com ADAL funcionarão nesta topologia, e as senhas não serão aproveitadas se, por exemplo, você desativar o uso de senhas com autenticação baseada em certificado.

__Descrição do tipo 4:__ Essa topologia bloqueia NTLM *externamente* e ma internamente. Permite que *todos os clientes* usem métodos de autenticação herdados *internamente* (até clientes compatíveis com Adal).

__Descrição do tipo 5:__ *externamente*, seus clientes de Adal modernos usarão o ma e quaisquer clientes que não oferecem suporte a Adal usarão métodos de autenticação herdados. No entanto, *internamente* , *todos os clientes* usarão autenticação herdada (incluindo todos os clientes compatíveis com Adal).

É muito fácil perder o controle da meta de proteger suas senhas nas opções disponíveis. Tenha em mente que a situação ideal é usar o MA externamente (por exemplo, configurando a autenticação baseada em certificado), para evitar ataques de DOS. Se você o aproveitar internamente para seus clientes modernos, você também se tornará o futuro da sua rede com relação aos ataques de DOS do Skype for Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por que usar set-CsAuthConfig no nível global

O `Set-CsAuthConfig` cmdlet afeta a configuração no registrador e nas funções de serviços Web.

Este cmdlet deve ser executado no nível global do Skype for Business Server. Ele *pode* ser executado no nível do pool, mas *não é recomendável* , pois ele adicionará complexidade à sua instalação. Executando esses comandos no nível do pool, se o seu pool não tiver todas as funções incluídas (por exemplo, ela não tem serviços Web), as configurações só serão definidas para a função registrador. Nesse caso, os serviços Web serão transportados com as configurações do nível global, o que pode ser um comportamento confuso (particularmente quando isso é feito sem intenção).

Se um cliente usar as configurações do registrador de um pool e as configurações dos serviços Web de outro pool e as configurações de autenticação estiverem em um estado inconsistente, os clientes do yous podem não conseguir fazer logon.

Além disso, se houver apenas uma função presente para um pool: 
* Set – só definirá as configurações que correspondem à função existente. Nenhum aviso especial será fornecido porque algumas configurações *não* foram definidas. 
* Get-retornará a configuração que corresponde à função existente e as configurações globais para a função que não existe.
* Se nenhuma função estiver presente para um pool, tanto Set como Get-retornará uma mensagem de erro.
* Se ambas as funções estiverem presentes para um pool, mas as políticas não forem definidas no nível do pool, Get-retornará uma mensagem de erro.

Talvez seja mais sensato fazer um get-para esses valores e fazer captura de tela ou gravar seu estado inicial antes de fazer qualquer alteração. Você também pode considerar manter um log de alterações em um OneNote.

> [!NOTE]
> 
> Observação: depois de configurar o CsAuthConfig, você deve executar o Enable-CsComputer em cada computador para que as configurações entrem em vigor.

> [!IMPORTANT]
> Se você estiver usando o Lync Web Access (LWA) e precisar usar o acesso baseado em formulários (FBA) para acesso externo, reconfigure o LWA para que os clientes possam acessá-lo com acesso anônimo para dar suporte a esses cenários. Da mesma forma, se você usar PIN de discagem, o FBA será bloqueado somente para usuários externos. Se for necessário alterar o PIN, será necessário fazer logon em sua empresa para fazer isso internamente.

> [!NOTE]
> 
> Se você usar o parâmetro BlockWindowsAuthExternally para bloquear o NTLM externamente, lembre-se de que o também bloqueia NTLM internamente para o canal SIP. No entanto, os clientes do Skype for Business e do Lync mais recentes do que 2010 ainda poderão fazer logon porque usarão NTLM sobre HTTP para entrar, internamente, e buscar um certificado para fazer logon via SIP. No entanto, os clientes mais antigos do que 2010 não poderão fazer logon internamente nessa circunstância, e você pode querer considerar a atualização desses aplicativos para que os usuários possam retomar a funcionalidade segura.

> [!IMPORTANT] 
> Alguns dos aplicativos da Web do Skype for Business não oferecem suporte ao MA. Portanto, usando o cenário BlockWindowsAuthExternallyAndInternally, você não poderá acessar esses aplicativos. Os aplicativos sem suporte a MA são Agendador da Web, página de discagem, painel de controle do Skype for Business (CSCP) e página de configurações do grupo de resposta. 

## <a name="links"></a>Links 
- Para obter mais informações sobre o PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obter mais orientações sobre como usar os comandos ou na CU necessária para instalá-los:
    - [Resumo de cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Atualizações do Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (geral)
    - O [Skype for Business Server 2015 de julho de 2018, componentes principais cu](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
