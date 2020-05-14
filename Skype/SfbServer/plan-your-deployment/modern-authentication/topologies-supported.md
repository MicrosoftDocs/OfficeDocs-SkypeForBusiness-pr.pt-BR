---
title: Topologias do Skype for Business compatíveis com a autenticação moderna
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
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Este artigo lista as topologias online e local compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança que se aplicam a cada topologia.
ms.openlocfilehash: 443980f6ecf2bdf170974bf0fdc0dd64f3657e67
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44219691"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologias do Skype for Business compatíveis com a autenticação moderna

Este artigo lista as topologias online e local compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança que se aplicam a cada topologia.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticação moderna no Skype for Business

O Skype for Business pode aproveitar as vantagens de segurança da autenticação moderna. Como o Skype for Business funciona em conjunto com o Exchange, o comportamento de logon que os usuários clientes do Skype for Business verão também serão afetados pelo status de MA do Exchange. Isso também se aplicará se você tiver uma divisão híbrida do Skype for Business. Há muitas partes em movimento, mas o objetivo aqui é uma lista fácil de Visualizar de topologias suportadas.

Dada o Skype for Business, o Skype for Business Online, o Exchange Server e o Exchange Online, quais topologias são compatíveis com o MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologias de MA compatíveis no Skype for Business

Há dois aplicativos de servidor potencialmente e duas cargas de trabalho do Microsoft 365 ou do Office 365, envolvidas nas topologias do Skype for Business usadas pelo MA.

- Skype for Business Server (CU 5) local

- Skype for Business online (SFBO)

- Exchange Server local

- Exchange Server online (EXO)

Outra parte importante do MA é saber onde a autenticação (Authn) e a autorização (authZ) dos usuários ocorrerão. As duas opções são:

- Azure AD, online na nuvem da Microsoft

- ADFS (servidor de Federação do Active Directory) no local

Portanto, ele se parece com isso, com o EXO e o SFBO na nuvem com o Azure AD e o Exchange Server (EXCH) e o Skype for Business Server (SFB) no local.

![Um exemplo de todos os aplicativos (Exchange e Skype for Business) e cargas de trabalho (EXO e SFBO) e os servidores de autorização (ADFS e evoSTS) que podem ser envolvidos ao ativar o MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Aqui estão as topologias com suporte. Por fim, observe a chave para os elementos gráficos:

- Se o ícone estiver esmaecido ou cinza, ele não será usado no cenário.

- O EXO é o Exchange Online.

- O SFBO é o Skype for Business online.

- O EXCH é o Exchange local.

- O SFB é o Skype for Business local.

- Os servidores de autorização são representados por triângulos, por exemplo, o AD do Azure é um triângulo com uma nuvem atrás dele.

- Pontos de setas no servidor de autorização que serão usados quando os clientes tentarem alcançar o recurso de servidor especificado.

Primeiro, vamos abordar o MA com o Skype for Business em topologias somente no local ou somente na nuvem.

> [!IMPORTANT]
> Você está pronto para configurar a autenticação moderna no Skype for Business Online? [Aqui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)estão as etapas para habilitar esse recurso.

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Somente na nuvem  <br/> |![SFB compatível com topologia MA, somente nuvem.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuários hospedados/caixas de correio localizadas: online  <br/> |O MA está ativado para EXO e SFBO.  <br/> Portanto, o servidor de autorização é o Azure AD.  <br/> |Autenticação multifator (MFA), autenticação baseada no certificado do cliente (CBA), acesso condicional (CA)/Mobile (gerenciamento de aplicativos) com o Intune. \*  <br/> |
|Somente local  <br/> |![SFB compatível com topologia MA, somente no local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuários hospedados/caixas de correio localizadas: local  <br/> |O MA está ativado para o SFB local.  <br/> Portanto, o servidor de autorização é AD FS.  <br/> Para obter detalhes de configuração, leia [Este artigo.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (somente para área de trabalho do Windows-não há suporte para clientes móveis). Nenhum recurso de integração do Exchange.  <br/><p> **Não recomendamos essa abordagem. Confira aqui:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> É recomendável que o estado MA seja o mesmo no Skype for Business e no Exchange (e em seus correspondentes online) para reduzir o número de prompts.

Topologias mistas envolvem combinações de híbridos de domínio dividido SFB. Estas são as topologias mistas com suporte no momento:

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Misto 1  <br/> |![SFB com suporte com topologia MA, mista 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO e SFB  <br/> |O MA não está habilitado para o SFB; nenhum recurso do SFB MA disponível nesta topologia.  <br/> |Nenhum recurso MA para o SFB.  <br/> |
|Misto 2  <br/> |![MA com suporte com topologia mista 2 do S4B, SFBO Plus MA trabalhando com o EXCH local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH e SFBO  <br/> |O MA está ativado apenas para SFBO. O servidor de autorização é o Azure AD para usuários hospedados no SFBO, mas o AD for EXCH no local.  <br/> |MFA, CBA, CA/MAM com o Intune.\*  <br/> |
|Misto 3  <br/> |![MA com suporte com SFB, EXO com MA ativado, mais EXCH e SFB no local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFB ou EXCH + SFB  <br/> |Nenhum recurso do SFB MA disponível nesta topologia  <br/> |Nenhum recurso MA para o SFB.  <br/> |
|Misto 4  <br/> |![MA com suporte com SFB, SFBO com MA ativado, mais EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH + SFBO ou EXCH + SFB  <br/> |O MA está ativado para SFBO, portanto, o servidor de autorização é o Azure AD para usuários hospedados no SFBO. Usuários locais no SFB e EXO usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|Misto 5  <br/> |![MA com suporte no SFB, EXO com MA e SFBO com MA e EXCH e SFB no local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está ativado tanto no EXO quanto no SFBO, portanto, o servidor de autorização é o Azure AD para usuários hospedados no SFBO; usuários locais no EXCH e no SFB usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|Misto 6  <br/> |![Em uma topologia mista de 6, a autenticação moderna está ativada nos quatro locais do possibile-o situtation ideal quando se trata de autenticação moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está em todos os lugares, portanto, o servidor de autorização é o Azure AD para todos os usuários. (online e local)  <br/>  Confira [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) as etapas de implantação. <br/> |MFA, CBA e CA/MAM (via Intune) para todos os usuários.  <br/> |

\*-O MFA inclui área de trabalho do Windows, MAC, iOS, dispositivos Android e Windows phones; O CBA inclui o Windows desktop, iOS e dispositivos Android; CA/MAM com o Intune, inclui dispositivos Android e iOS.

> [!IMPORTANT]
> É muito importante observar que os usuários podem ver **vários prompts** em alguns casos, notavelmente onde o estado ma não é o mesmo em todos os recursos do servidor que os clientes podem precisar e solicitar, como é o caso com todas as versões das topologias mistas.

> [!IMPORTANT]
> Observe também que, em alguns casos (misto 1, 3 e 5 especificamente), uma chave do registro [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) deve ser definida para a configuração adequada para clientes da área de trabalho do Windows.


