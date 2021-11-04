---
title: Planejando desativar os métodos de autenticação herdou interna e externamente para sua rede
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Este artigo descreve os cmdlets que dão aos administradores mais controle dos métodos de autenticação usados dentro e fora de uma empresa. Os administradores podem ativar ou desativar os métodos de autenticação internamente ou externamente para sua rede.
ms.openlocfilehash: 65ec31dcd4a320b42da746eece41009f70e886af
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777951"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planejando desativar os métodos de autenticação herdou interna e externamente para sua rede.

> [!NOTE]
> Se você estiver prestes a ler este artigo, já deve saber sobre topologias de Autenticação Moderna suportadas, ADAL e sobre a configuração de Autenticação Moderna, mas, caso não saiba, aqui estão os artigos que você precisa começar: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](./topologies-supported.md)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](/skypeforbusiness/manage/authentication/use-adal)
  
A Autenticação Moderna não apenas habilita métodos mais seguros de autenticação, como Two-Factor Auth ou Autenticação baseada em certificado, ela pode realizar a autorização do usuário sem precisar de um nome de usuário ou senha também. É muito útil.

Este artigo ajudará você a conectar os buracos que foram explorados para ataques de Negação de Serviço (DOS) em servidores Skype for Business, desligando métodos mais antigos usados para autenticação, externamente, internamente ou ambos, para sua rede. Por exemplo, um bom método para ajudar a parar ataques de DOS seria desativar Windows Autenticação Integrada (que inclui NTLM e Kerberos). Desligar o NTLM externamente e confiar na autenticação baseada em certificado ajuda a proteger senhas contra exposição. Isso porque o NTLM usa credenciais de senha para autenticar usuários, mas a autenticação baseada em certificado , habilitada pela Modern Auth, não. Isso significa que uma opção ideal para reduzir ataques de DOS é bloquear o NTLM externamente e usar apenas a autenticação baseada em certificados.

Tudo bem, vamos começar.

## <a name="what-would-you-be-changing"></a>O que você estaria mudando? 

Esses cmdlets funcionam para pontos de acesso SIP e Serviços Web. Embora esses dois canais usem métodos de acesso diferentes, executando a gama de NTLM e Kerberos para acesso anônimo, todos os métodos padrão usados pelo Skype for Business foram levados em consideração.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Como obter os cmdlets Get e Set-CsAuthConfig

Esses cmdlets serão instalados somente após a atualização cumulativa de julho de 2018 (6.0.9319.534) para o Microsoft Skype for Business Server 2015 e, em seguida, você tem uma variedade de topologias que podem ser implantadas para seu servidor Skype for Business.

## <a name="topologies"></a>Topologias

É importante ter em mente que essas são as Topologias Com Suporte envolvidas neste cenário! Se você precisar ir até Suporte para ajudar a bloquear um método, por exemplo, você precisará ter uma configuração entre os tipos abaixo. 

> [!IMPORTANT]
> Na tabela e descrições *abaixo,* Autenticação Moderna é abreviada como __MA__ e Windows *Autenticação* Integrada é abreviada como __Win__. Como lembrete, Windows Autenticação Integrada é formada por dois métodos: autenticação NTLM e Kerberos. Você precisará saber disso para ler a tabela corretamente!


|       |Externamente  |Internamente  |Parâmetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Descrição do tipo 1:__ Esse é o cenário padrão quando o MA está __ligado__ para Skype for Business Server. Em outras palavras, este é o *ponto de partida quando* o MA é configurado.

__Descrição do tipo 2:__ Essa topologia bloqueia o NTLM externamente , mas permite que NTLM ou Kerberos (para clientes que não suportam a ADAL) *funcionem internamente.* Se seus clientes deem suporte ao ADAL, eles usarão a MA internamente.

__Descrição do tipo 3:__ Essa topologia requer MA para todos os usuários. Todos os seus clientes com capacidade ADAL funcionarão nessa topologia, e as senhas não serão aproveitadas se, por exemplo, você desativar o uso de senhas com a Auth baseada em certificado.

__Descrição do tipo 4:__ Essa topologia bloqueia o NTLM *externamente* e o MA internamente. Ele permite que *todos os clientes* usem métodos de autenticação herdado *internamente* (até mesmo clientes com capacidade para ADAL).

__Tipo 5 Descrição:__ *Externamente*, seus clientes modernos ADAL usarão MA e quaisquer clientes que não suportam a ADAL usarão métodos de autenticação herdados. Mas, *internamente,* *todos os clientes* usarão autenticação herdda (incluindo todos os clientes com capacidade ADAL).

É muito fácil perder o controle da meta de proteger suas senhas nas opções disponíveis. Lembre-se de que a situação ideal é usar a MA externamente (por exemplo, configurando autth baseada em certificado), para evitar ataques dos DOS. Se você aproveitar internamente para seus clientes modernos, você também provará a sua rede em relação aos ataques Skype for Business Server DOS.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por que usar Set-CsAuthConfig no nível global

O `Set-CsAuthConfig` cmdlet afeta a configuração tanto no Registrador quanto nas funções dos Serviços Web.

Esse cmdlet deve ser executado no nível global do servidor Skype for Business. Ele *pode* ser executado no nível pool, mas isso não *é recomendado* porque adicionará complexidade à sua instalação. Ao executar esses comandos no nível pool, se o Pool não tiver todas as funções incluídas (por exemplo, ele não tem Serviços Web), as configurações serão definidas apenas para a função Registrador. Nesse caso, os Serviços Web continuarão com configurações do nível Global, o que pode ser um comportamento confuso (particularmente quando isso é feito sem intencionalidade).

Se um cliente usa as configurações do Registrador de um pool e as configurações dos Serviços Web de outro pool e as configurações de autenticação estão em um estado inconsistente, talvez os clientes não possam fazer logoff.

Além disso, se houver apenas uma função presente para um pool: 
* Set- definirá apenas as configurações que correspondem à função existente. Nenhum aviso especial será dado porque algumas configurações não *foram definidas.* 
* Get- retornará a configuração que corresponde à função existente e as configurações Globais para a função que não existe.
* Se nenhuma das funções estiver presente para um pool, Set e Get retornarão uma mensagem de erro.
* Se ambas as funções estão presentes para um pool, mas as políticas não são definidas no nível do pool, Get- retornará uma mensagem de erro.

Talvez seja mais sensato fazer um Get- para esses valores e para captura de tela ou gravar seu estado inicial antes de fazer quaisquer alterações. Você também pode considerar manter um log de alterações em um OneNote.

> [!NOTE]
> 
> Observação: depois de configurar o CsAuthConfig, você deve executar Enable-CsComputer em cada computador para que as configurações entre em vigor.

> [!IMPORTANT]
> Se você estiver usando o Lync Web Access (LWA) e tiver que usar o Acesso Baseado em Formulários (FBA) para acesso externo, reconfigure o LWA para que os clientes possam acessá-lo com Acesso Anônimo para dar suporte a esses cenários. Da mesma forma, se você usar Pin Discado, o FBA será bloqueado somente para usuários externos. Se eles precisarem alterar o pin, eles precisarão fazer logon na empresa para fazer isso, internamente.

> [!NOTE]
> 
> Se você usar o parâmetro BlockWindowsAuthExternally para bloquear externamente o NTLM, saiba que isso também bloqueia o NTLM internamente para o canal SIP. No entanto, Skype for Business clientes do Skype for Business e do Lync mais novos do que 2010 ainda poderão fazer logon porque eles usarão o NTLM sobre HTTP para entrar, internamente, e buscar um certificado para fazer logon sobre SIP. No entanto, clientes com mais de 2010 não poderão fazer logon internamente nessa circunstância, e talvez você queira considerar atualizar esses aplicativos para que seus usuários possam retomar a funcionalidade segura.

> [!IMPORTANT] 
> Alguns dos aplicativos Skype for Business Web não suportam MA. Portanto, usando o cenário BlockWindowsAuthExternallyAndInternally, você não poderá acessar esses aplicativos. Os aplicativos sem suporte para MA são Agendador da Web, Página discada, Skype for Business Painel de Controle (CSCP) e Página de Configurações Grupo de Resposta. 

## <a name="links"></a>Links 
- Para obter mais informações do PowerShell:
    -  [Get-CsAuthConfig](/powershell/module/skype/get-csauthconfig?view=skype-ps)
    -  [Set-CsAuthConfig](/powershell/module/skype/set-csauthconfig?view=skype-ps)

- Para obter mais informações sobre como usar os comandos ou na CU necessária para instalá-los:
    - [Reunião de cmdlets](https://support.microsoft.com/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - [Atualizações para Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015) (Geral)
    - Os componentes principais CU (6.0.9319.534) de julho de [2018 Skype for Business Server 2015](https://support.microsoft.com/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)


