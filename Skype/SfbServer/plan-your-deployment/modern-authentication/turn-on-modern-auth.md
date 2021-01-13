---
title: Planejando desativar os métodos de autenticação herdam interna e externamente para sua rede
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Este artigo descreve cmdlets que dão aos administradores mais controle dos métodos de autenticação usados dentro e fora de uma empresa. Os administradores podem ativar ou desativar os métodos de autenticação internamente ou externamente em sua rede.
ms.openlocfilehash: dca7dca332564442110c626a222f7ed5d138efaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810021"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planejamento para desativar os métodos de autenticação herdam interna e externamente para sua rede.

> [!NOTE]
> Se estiver prestes a ler este artigo, você já deve saber sobre topologias de Autenticação Moderna suportadas, ADAL e sobre a configuração de Autenticação Moderna, mas, caso não o tenha, aqui estão os artigos que você precisa começar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
A Autenticação Moderna não apenas habilita métodos mais seguros de autenticação, como autenticação Two-Factor autenticação ou autenticação baseada em certificado, ela pode realizar a autorização do usuário sem precisar de um nome de usuário ou senha também. É bastante útil.

Este artigo ajudará você a conectar buracos que foram explorados por ataques de Negação de Serviço (DOS) no Skype for Business Servers, ao desligar os métodos mais antigos usados para autenticação, externamente, internamente ou ambos, para sua rede. Por exemplo, um bom método para ajudar a parar ataques dos DOS seria desativar a Autenticação Integrada do Windows (que inclui NTLM e Kerberos). Desligar o NTLM externamente e confiar na autenticação baseada em certificado ajuda a proteger senhas contra exposição. Isso porque o NTLM usa credenciais de senha para autenticar usuários, mas a autenticação baseada em certificado , habilitada pela Autenticação Moderna, não. Isso significa que uma opção ideal para reduzir ataques dos DOS é bloquear o NTLM externamente e usar apenas a autenticação baseada em certificado.

Vamos começar.

## <a name="what-would-you-be-changing"></a>O que você alteraria? 

Esses cmdlets funcionam para pontos de acesso sip e serviços Web. Embora esses dois canais usem métodos de acesso diferentes, executando a gama de NTLM e Kerberos para acesso anônimo, todos os métodos padrão usados pelo Skype for Business foram levados em consideração.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Como obter os cmdlets Get e Set-CsAuthConfig

Esses cmdlets só serão instalados após a atualização cumulativa de julho de 2018 (6.0.9319.534) do Microsoft Skype for Business Server 2015 e, em seguida, você terá uma variedade de topologias que podem ser implantadas para seu servidor do Skype for Business.

## <a name="topologies"></a>Topologias

É importante ter em mente que estas são as Topologias com Suporte envolvidas neste cenário! Se você precisar ir para Suporte para ajuda com o bloqueio de um método, por exemplo, você precisará ter uma configuração entre os tipos abaixo. 

> [!IMPORTANT]
> Na tabela e descrições *abaixo,* a Autenticação Moderna é abreviada como __MA__ e a Autenticação Integrada do *Windows* é abreviada como __Win__. Como lembrete, a Autenticação Integrada do Windows é formada por dois métodos: autenticação NTLM e Kerberos. Você precisará saber disso para ler a tabela corretamente!


|       |Externamente  |Internamente  |Parâmetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Tipo 1 Descrição:__ Esse é o cenário padrão quando a am é __responsabilidade do__ Skype for Business Server. Em outras palavras, esse é o *ponto de partida* quando a am está configurada.

__Tipo 2 Descrição:__ Essa topologia bloqueia o NTLM *externamente,* mas permite que NTLM ou Kerberos (para clientes que não suportam a ADAL) funcionem *internamente.* Se seus clientes deem suporte à ADAL, eles usarão a MA internamente.

__Tipo 3 Descrição:__ Essa topologia requer ma para todos os usuários. Todos os seus clientes com capacidade para ADAL funcionarão nessa topologia, e as senhas não serão aproveitadas se, por exemplo, você desativar o uso de senhas com a Auth baseada em certificado.

__Tipo 4 Descrição:__ Essa topologia bloqueia NTLM *externamente* e o MA internamente. Ele permite que *todos os clientes* usem internamente métodos de autenticação *herdado* (até mesmo clientes com ADAL).

__Tipo 5 Descrição:__ *externamente,* seus clientes modernos da ADAL usarão a autenticação moderna e todos os clientes que não deem suporte à ADAL usarão métodos de autenticação herdados. Porém, *internamente,* *todos os clientes* usarão a autenticação herdda (incluindo todos os clientes com ADAL).

É muito fácil perder o controle da meta de proteger suas senhas nas opções disponíveis. Lembre-se de que a situação ideal é usar a ma externamente (por exemplo, configurando a auth baseada em certificado), para evitar ataques do DOS. Se você a utilizar internamente para seus clientes modernos, também mostrará sua rede com relação aos ataques do Skype for Business Server DOS.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por que usar Set-CsAuthConfig no nível Global

O `Set-CsAuthConfig` cmdlet afeta a configuração nas funções Registrador e Serviços Web.

Este cmdlet deve ser executado no nível Global do seu servidor do Skype for Business. Ele *pode* ser executado no nível do Pool, mas isso não *é recomendado* porque adicionará complexidade à sua instalação. Ao executar esses comandos no nível do Pool, se o pool não tiver todas as funções incluídas (por exemplo, se não tiver Serviços Web), as configurações serão definidas apenas para a função Registrador. Nesse caso, os Serviços Web continuarão com configurações do nível Global, o que pode ser um comportamento confuso (especialmente quando isso é feito involutionamente).

Se um cliente usar as configurações de Registrador de um pool e as configurações dos Serviços Web de outro pool e as configurações de autenticação estiver em um estado inconsistente, talvez os clientes não possam fazer logoff.

Além disso, se houver apenas uma função presente para um pool: 
* Set- definirá apenas as configurações que correspondem à função existente. Nenhum aviso especial será dado porque algumas configurações não *foram definidas.* 
* Get- retornará a configuração que corresponde à função existente e as configurações Globais para a função que não existe.
* Se nenhuma função estiver presente para um pool, Set- e Get retornarão uma mensagem de erro.
* Se ambas as funções estão presentes para um pool, mas as políticas não estão definidas no nível do pool, Get- retornará uma mensagem de erro.

Talvez seja mais sensato fazer um Get- para esses valores e para fazer uma captura de tela ou registrar seu estado inicial antes de fazer qualquer alteração. Você também pode considerar manter um log de alterações em um OneNote.

> [!NOTE]
> 
> Observação: depois de configurar o CsAuthConfig, você deve executar Enable-CsComputer em cada computador para que as configurações entre em vigor.

> [!IMPORTANT]
> Se você estiver usando o Lync Web Access (LWA) e tiver que usar o Acesso Baseado em Formulários (FBA) para acesso externo, reconfigure o LWA para que os clientes possam acessá-lo com Acesso Anônimo para dar suporte a esses cenários. Da mesma forma, se você usar o Pin de Discagem, o FBA será bloqueado somente para usuários externos. Se precisar alterar o pin, será necessário entrar em sua corporação para fazer isso internamente.

> [!NOTE]
> 
> Se você usar o parâmetro BlockWindowsAuthExternally para bloquear externamente o NTLM, saiba que isso também bloqueia o NTLM internamente para o canal SIP. No entanto, os clientes do Skype for Business e do Lync com mais de 2010 ainda poderão fazer logon porque usarão NTLM sobre HTTP para entrar internamente e, em seguida, buscar um certificado para fazer logon via SIP. No entanto, os clientes mais antigos do que 2010 não poderão fazer logon internamente nessa circunstância, e talvez você queira considerar a atualização desses aplicativos para que os usuários possam retomar a funcionalidade segura.

> [!IMPORTANT] 
> Alguns dos aplicativos Web do Skype for Business não são suportados por ma. Portanto, usando o cenário BlockWindowsAuthExternallyAndInternally, você não poderá acessar esses aplicativos. Os aplicativos sem suporte a MA são Agendador da Web, Página de Discagem, Painel de Controle do Skype for Business (CSCP) e Página de Configurações do Grupo de Resposta. 

## <a name="links"></a>Links 
- Para obter mais informações do PowerShell:
    -  [Get-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](https://docs.microsoft.com/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obter mais direção sobre como usar os comandos ou sobre a cu necessária para instalá-los:
    - [Resumo de cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Atualizações do Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (Geral)
    - The [July 2018 Skype for Business Server 2015, Core Components CU](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server) (6.0.9319.534)


 
