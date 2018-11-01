---
title: Planejamento para desativar os métodos de autenticação Legacy interna e externamente à sua rede
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: ''
description: Os cmdlets este artigo contornos que dão admins mais controle dos métodos de autenticação usado dentro e fora, de uma empresa. Os administradores podem ativar métodos de autenticação ou desativar interna ou externamente para sua rede.
ms.openlocfilehash: 57b51a897f476d5c4b4b17ccda8ffe074f8a26cd
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839761"
---
# <a name="planning-to-turn-off-legacy-authentication-methods-internally-and-externally-to-your-network"></a>Planejamento desativar os métodos de autenticação Legacy interna e externamente à sua rede.

> [!NOTE]
> Se você está prestes a ler este artigo, você já deve conhecer topologias com suporte de autenticação moderno, ADAL, e sobre a configuração de autenticação moderno, mas, caso contrário, aqui estão os artigos que você precisa iniciar o check-out: 
>  + [https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)
>  + [https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal](https://docs.microsoft.com/skypeforbusiness/manage/authentication/use-adal)
  
Autenticação moderna apenas não ativa o mais seguros métodos de autenticação, como autenticação de dois fatores, ou a autenticação baseada em certificado, ele pode realizar a autorização do seu usuário sem a necessidade de um usuário ou senha muito. Ele é muito útil.

Este artigo ajudará você plug falhas que tenham sido exploradas para ataques de negação de serviço (DOS) no Skype para servidores de negócios, desativando mais antigos métodos usados para autenticação, externamente, internamente, ou ambos, à sua rede. Por exemplo, um método bom para ajudar a impedir ataques DOS seria desativar a autenticação integrada do Windows (que inclui o NTLM e Kerberos). Desativando a NTLM externamente e contar com autenticação baseada em certificado ajuda a proteger senhas de exposição. Isso ocorre porque o NTLM usa as credenciais de senha para autenticar usuários, mas não de autenticação baseada em certificado – habilitada por Auth moderno –. Que significa uma opção ideal para reduzir ataques DOS é bloco NTLM externamente e usar somente autenticação baseada em certificado, em vez disso.

Tudo bem, vamos começar.

## <a name="what-would-you-be-changing"></a>O que poderia ser mudando? 

Esses cmdlets funcionam com pontos SIP e serviços Web do access. Embora esses dois canais usam os métodos de acesso diferente, executam a gama de NTLM e Kerberos para acesso anônimo, todos os métodos padrão usados pelo Skype para negócios foram levados em consideração.

## <a name="how-to-get-the-get--and-set-csauthconfig-cmdlets"></a>Como obter os cmdlets Get - e Set-CsAuthConfig

Esses cmdlets só serão instalados postar julho de 2018 atualização cumulativa (6.0.9319.534) para Microsoft Skype para Business Server 2015 e, em seguida, você tem uma variedade de topologias que podem ser expandidos check-out para seu Skype para Business server.

## <a name="topologies"></a>Topologias

É importante ter em mente que essas são as topologias com suporte envolvidos neste cenário! Se você precisar vá em suporte para obter ajuda com um método de bloqueio, por exemplo, você precisará ter uma configuração entre os tipos abaixo. 

> [!IMPORTANT]
> Na tabela e descrições abaixo, *Autenticação moderno* será abreviado como __MA__ e *Autenticação integrada do Windows* será abreviado como __Win__. Como um lembrete, autenticação integrada do Windows é composta pelos dois métodos: autenticação NTLM e Kerberos. Você precisará saber se isso ao ler a tabela adequadamente!


|       |Externamente  |Internamente  |Parâmetro  |
|---------|:---------|:---------|---------|
|__Tipo 1__   |  MA + Win       | MA + Win         |  AllowAllExternallyAndInternally       |
|__Tipo 2__   |  MA       | MA + Win         | BlockWindowsAuthExternally        |
|__Tipo 3__   |  MA       | MA        | BlockWindowsAuthExternallyAndInternally        |
|__Tipo 4__   |  MA       | Win        | BlockWindowsAuthExternallyAndModernAuthInternally    |
|__Tipo 5__   |  MA + Win       | Win        | BlockModernAuthInternally         |

__Digite 1 Descrição:__ Este é o padrão __cenário quando MA é ativado para Skype para Business Server__ . Em outras palavras, isso é o *ponto de partida* quando MA está configurada.

__Descrição do tipo 2:__ Essa topologia bloqueia NTLM *externamente*, mas permite que o NTLM ou Kerberos (para clientes que não oferecem suporte a ADAL) funcione *internamente*. Se seus clientes suportam ADAL eles usarão MA internamente.

__Descrição do tipo 3:__ Esta topologia requer MA para todos os usuários. Todos os seus clientes capaz de ADAL funcionará nessa topologia e senhas não serão aproveitadas se, por exemplo, desativar o uso de senhas com autenticação baseada em certificado

__Descrição do tipo 4:__ Essa topologia bloqueia NTLM *externamente* e MA internamente. Ele permite que *todos os clientes* usem autenticação herdado métodos *internamente* (pares capaz de ADAL clientes).

__Descrição do tipo 5:__ *Externamente*, os clientes ADAL modernos usará MA e todos os clientes que não há suporte para ADAL usará os métodos de autenticação de legado. Porém, *todos os clientes* *internamente* usará a autenticação herdada (incluindo todos os clientes capaz de ADAL).

É muito fácil perder o controle da meta de proteger suas senhas nas opções disponíveis. Tenha em mente a situação ideal é usar MA externamente (por exemplo, para configurar autenticação baseada em certificado), para evitar ataques DOS. Se você aproveitá-lo internamente para que os clientes modernos, você vai também obsoleta sua rede relacionadas Skype para Business Server DOS ataques.

## <a name="why-to-use-set-csauthconfig-at-the-global-level"></a>Por que usar Set-CsAuthConfig no nível Global

O `Set-CsAuthConfig` efeitos da configuração de cmdlet no registrador e as funções de serviços da Web.

Esse cmdlet é destinado a ser executado no nível Global de sua Skype para Business server. Ele *pode* ser executado no nível de Pool, mas isto é *não recomendado* , porque ele adicionará complexidade à sua instalação. Executando estes comandos no nível do Pool, se o Pool não tiver todas as funções incluídas (por exemplo, se ele não tiver serviços da Web), as configurações só serão definidas para a função registrador. Nesse caso, os serviços Web irá cumprir com as configurações no nível Global, que pode ser confuso comportamento (especialmente quando isso é feito acidentalmente).

Se um cliente usa as configurações de um pool de registrador e as configurações de serviços da Web de outro pool e as configurações de autenticação estão em um estado inconsistente, clientes yous podem não conseguir fazer logon.

Além disso, se houver apenas uma função presente para um pool: 
* Set-vão apenas definir as configurações que correspondem à função que existe. Nenhum aviso especial receberá porque algumas configurações eram *não* definido. 
* Get-irá retornar a configuração que corresponde à função que existe e as configurações globais para a função que não existe.
* Se nenhuma função estiver presente para um pool, ambos os Set - e Get-será retornar uma mensagem de erro.
* Se ambas as funções estão presentes para um pool, mas as diretivas não são definidas no nível do pool, Get-irá retornar uma mensagem de erro.

Talvez seja wisest fazer um Get-para esses valores e para a captura de tela ou registrar seu estado inicial antes de fazer alterações. Você também pode considerar a capacidade de manter um log de alterações em um OneNote.

> [!IMPORTANT]
> Se você estiver usando o Lync Web Access (LWA) e deve usar o acesso baseada em formulários (FBA) para acesso externo, reconfigure LWA para que os clientes podem acessá-lo com acesso anônimo para oferecer suporte a esses cenários. Da mesma forma, se você usar um Pin de discagem, FBA será bloqueado para apenas usuários externos. Se eles precisarem alterar seu pin, precisará fazer logon no seu corporation para fazê-lo, internamente.

## <a name="links"></a>Links ##
- Para obter mais informações PowerShell:
    - Get-CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Get-CsAuthConfig.md)
    - Set-CsAuthConfig[https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md](https://github.com/MicrosoftDocs/office-docs-powershell/blob/master/skype/skype-ps/skype/Set-CsAuthConfig.md)

- Para mais orientações sobre como usar os comandos ou na CU necessária para instalá-las:
    - Resumo de cmdlets[https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication](https://support.microsoft.com/en-us/help/4346673/new-cmdlets-to-manage-skype-for-business-server-2015-authentication)
    - Atualizações do Skype para Business Server 2015 (geral)[https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015)
    - O Skype julho de 2018 para Business Server 2015, Core Components CU (6.0.9319.534)[https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server](https://support.microsoft.com/en-us/help/4340903/july-2018-cumulative-update-6-0-9319-534-for-skype-for-business-server)


 