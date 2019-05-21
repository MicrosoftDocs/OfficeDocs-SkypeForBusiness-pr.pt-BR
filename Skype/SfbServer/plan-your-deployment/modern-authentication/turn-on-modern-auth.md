---
title: Planejando desativar métodos de autenticação herdados interna e externamente para a sua rede
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Este artigo descreve os cmdlets que dão aos administradores mais controle dos métodos de autenticação usados dentro e fora de uma empresa. Os administradores podem ativar ou desativar os métodos de autenticação interna ou externamente em sua rede.
ms.openlocfilehash: aaee46b04832cc114f895f905c180fe089d7349d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297264"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planejando desativar métodos de autenticação herdados interna e externamente para a sua rede.

> [!NOTE]
> Se você estiver prestes a ler este artigo, você já deve saber sobre topologias de autenticação modernas, ADAL e sobre a configuração de autenticação moderna, mas, caso contrário, aqui estão os artigos que você precisa para começar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
A autenticação moderna não apenas habilita métodos mais seguros de autenticação, como autenticação de dois fatores ou autenticação baseada em certificado, pode executar a autorização do seu usuário sem precisar de um nome de usuário ou senha. É muito prático.

Este artigo ajudará você a conectar brechas que foram exploradas por ataques de negação de serviço (DOS) nos servidores do Skype for Business, desativando os métodos mais antigos usados para autenticação, externamente, internamente ou ambos, à sua rede. Por exemplo, um método bom para ajudar a evitar ataques DOS seria desativar a autenticação integrada do Windows (que inclui NTLM e Kerberos). Desativar o NTLM externamente e confiar na autenticação baseada em certificado ajuda a proteger senhas contra exposição. Isso ocorre porque o NTLM usa credenciais de senha para autenticar usuários, mas a autenticação baseada em certificado – habilitada pela autenticação moderna – não. Isso significa que uma opção ideal para reduzir os ataques DOS é bloquear o NTLM externamente e usar somente a autenticação baseada em certificado ali, em vez disso.

Tudo certo, vamos começar.

## <a name="what-would-you-be-changing"></a>O que você mudaria? 

Esses cmdlets funcionam para pontos de acesso SIP e de serviços Web do Access. Embora esses dois canais usem métodos de acesso diferentes, executando a gama do NTLM e Kerberos para acesso anônimo, todos os métodos padrão usados pelo Skype for Business foram levados em consideração.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Como obter os cmdlets Get e Set-CsAuthConfig

Esses cmdlets só serão instalados na atualização cumulativa do post de julho de 2018 (6.0.9319.534) para o Microsoft Skype for Business Server 2015, e você terá uma variedade de topologias que podem ser implantadas para o seu servidor do Skype for Business.

## <a name="topologies"></a>Topologia

É importante ter em mente que essas são as topologias com suporte envolvidas nesse cenário! Se você precisar acessar o suporte para obter ajuda para bloquear um método, por exemplo, será necessário ter uma configuração entre os tipos abaixo. 

> [!IMPORTANT]
> Na tabela e descrições abaixo, a *autenticação moderna* é abreviada como __ma__ e a *autenticação integrada do Windows* é abreviada como __Win__. Como lembrete, a autenticação integrada do Windows é composta por dois métodos: autenticação NTLM e Kerberos. Você precisará saber isso para ler a tabela corretamente!


|       |Externamente  |Internas  |Parâmetro  |
|---------|:---------|:---------|---------|
|__Digite 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win32        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win32        | BlockModernAuthInternally         |

__Digite 1 Descrição:__ Esse é o cenário padrão quando o MA está ____ ativado para o Skype for Business Server. Em outras palavras, esse é o *ponto de partida* quando o ma está configurado.

__Digite 2 Descrição:__ Essa topologia bloqueia NTLM *externamente*, mas permite que NTLM ou Kerberos (para clientes que não oferecem suporte a Adal) funcionem *internamente*. Se seus clientes dão suporte a ADAL, eles usarão o MA internamente.

__Digite 3 Descrição:__ Essa topologia exige MA para todos os usuários. Todos os seus clientes compatíveis com o ADAL funcionarão nessa topologia, e as senhas não serão aproveitadas se, por exemplo, você desativar o uso de senhas com autenticação baseada em certificado.

__Digite 4 Descrição:__ Essa topologia bloqueia NTLM *externamente* e ma internamente. Ele permite que *todos os clientes* usem métodos de autenticação herdados *internamente* (inclusive clientes compatíveis com o Adal).

__Digite 5 Descrição:__ *Externamente*, seus clientes de Adal modernos usarão ma e qualquer cliente que não dê suporte a Adal usará métodos de autenticação herdados. Mas, *internamente* , *todos os clientes* usarão autenticação herdada (incluindo todos os clientes compatíveis com o Adal).

É bem fácil perder o controle da meta de proteger suas senhas nas opções disponíveis. Lembre-se de que a situação ideal é usar o MA externamente (por exemplo, configurando autenticação baseada em certificados) para evitar ataques de DOS. Se você aproveitá-lo internamente para seus clientes modernos, você também passará a usar o Skype para a sua rede com relação aos ataques de DOS do Skype for Business Server.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por que usar set-CsAuthConfig no nível global

O `Set-CsAuthConfig` cmdlet afeta a configuração nas funções de serviços Web registrador e serviços Web.

Este cmdlet deve ser executado no nível global do seu Skype for Business Server. Ele *pode* ser executado no nível do pool, mas *não é recomendado* porque ele adicionará complexidade à sua instalação. Ao executar esses comandos no nível do pool, se o pool não tiver todas as funções incluídas (por exemplo, ela não tem serviços Web), as configurações só serão definidas para a função de registrador. Nesse caso, os serviços Web serão transferidos com as configurações do nível global, o que pode ser um comportamento confuso (especialmente quando isso é feito de forma não intencional).

Se um cliente usar as configurações de registrador de um pool e as configurações de serviços Web de outro pool e as configurações de autenticação estiverem em um estado inconsistente, os clientes do yous não poderão fazer logon.

Além disso, se houver apenas uma função presente para um pool: 
* Set-só definirá as configurações que correspondem à função que existe. Nenhum aviso especial será fornecido porque algumas configurações *não* foram definidas. 
* Get-retornará a configuração correspondente à função existente e as configurações globais para a função que não existe.
* Se nenhuma função estiver presente para um pool, tanto Set-and Get-retornará uma mensagem de erro.
* Se ambas as funções estiverem presentes para um pool, mas as políticas não forem definidas no nível do pool, Get-retornará uma mensagem de erro.

Pode ser mais sensato fazer um get-para esses valores e fazer uma captura de tela ou gravar o estado inicial antes de fazer qualquer alteração. Você também pode considerar manter um log das alterações em um OneNote.

> [!NOTE]
> 
> Observação: depois de configurar o CsAuthConfig, você deve executar Enable-CsComputer em cada computador para que as configurações entrem em vigor.

> [!IMPORTANT]
> Se você estiver usando o Lync Web Access (LWA) e deve usar acesso baseado em formulários (FBA) para acesso externo, reconfigure o LWA para que os clientes possam acessá-lo com acesso anônimo para dar suporte a esses cenários. Da mesma forma, se você usar o PIN de discagem, a FBA será bloqueada somente para usuários externos. Se precisar mudar seu PIN, será preciso fazer login na corporação para fazê-lo internamente.

## <a name="links"></a>Links 
- Para obter mais informações sobre o PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/en-us/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obter mais orientações sobre como usar os comandos ou na RECOR necessária para instalá-los:
    - [Resumindo cmdlets](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Atualizações para o Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015) Geralmente
    - O [Skype for Business Server 2015 de julho de 2018, componentes principais recor](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
