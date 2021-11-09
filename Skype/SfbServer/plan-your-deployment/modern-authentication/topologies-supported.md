---
title: Topologias do Skype for Business compatíveis com a Autenticação Moderna
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Este artigo lista quais topologias online e locais têm suporte com Autenticação Moderna no Skype for Business, bem como recursos de segurança que se aplicam a cada topologia.
ms.openlocfilehash: ed6710e0f25e946e8cb9e7034300bd450dd07baa
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60835069"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologias do Skype for Business compatíveis com a Autenticação Moderna

Este artigo lista quais topologias online e locais têm suporte com Autenticação Moderna no Skype for Business, bem como recursos de segurança que se aplicam a cada topologia.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticação moderna no Skype for Business

Skype for Business pode aproveitar as vantagens de segurança da Autenticação Moderna. Como Skype for Business funciona de perto com Exchange, o comportamento de logon que os usuários clientes Skype for Business ver também serão afetados pelo status ma do Exchange. Isso também se aplicará se você tiver um Skype for Business híbrido de domínio dividido. São muitas partes móveis, mas o objetivo aqui é uma lista fácil de visualizar topologias com suporte.

Considerando Skype for Business, Skype for Business online, Exchange Server e Exchange online, quais topologias são suportadas com MA?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologias MA com suporte em Skype for Business

Há potencialmente dois aplicativos de servidor e duas cargas de trabalho Microsoft 365 ou Office 365, envolvidas com Skype for Business topologias usadas pelo MA.

- Skype for Business servidor (CU 5) local

- Skype for Business online (SFBO)

- Exchange servidor local

- Exchange servidor online (EXO)

Outra parte importante do MA é saber onde ocorrerá a autenticação (authN) e a autorização (authZ) dos usuários. As duas opções são:

- Azure AD, online no Microsoft Cloud

- Servidor de Federação do Active Directory (ADFS) local

Portanto, ele se parece um pouco com isso, com EXO e SFBO na nuvem com o Azure AD, e Exchange Server (EXCH) e servidor Skype for Business (SFB) no local.

![Um exemplo de todos os aplicativos (Exchange e Skype for Business) e cargas de trabalho (EXO e SFBO) e ambos os servidores de autorização (ADFS e evoSTS) que podem ser envolvidos ao ligar o MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Aqui estão as topologias suportadas. Observe a chave para os elementos gráficos:

- Se o ícone estiver esmaecida ou cinza, ele não será usado no cenário.

- EXO é Exchange Online.

- SFBO é Skype for Business Online.

- O EXCH Exchange local.

- SFB é Skype for Business local.

- Os servidores de autorização são representados por triângulos, por exemplo, o Azure AD é um triângulo com uma nuvem atrás dele.

- As setas apontam para o servidor de autorização que será usado quando os clientes tentarem alcançar o recurso de servidor especificado.

Primeiro, vamos abranger a ma com Skype for Business em topologias somente no local ou somente na nuvem.

> [!IMPORTANT]
> Você está pronto para configurar a Autenticação Moderna no Skype for Business Online? As etapas para habilitar esse recurso estão [aqui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx).

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Somente na nuvem  <br/> |![SFB com suporte com topologia MA, somente nuvem.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuários localizados em casas/caixas de correio: Online  <br/> |O MA está no EXO e no SFBO.  <br/> Portanto, o servidor de autorização é o Azure AD.  <br/> |Autenticação multifacional (MFA), autenticação baseada em certificado de cliente (CBA), Acesso Condicional (CA)/Gerenciamento de Aplicativo Móvel (MAM) com o Intune. \*  <br/> |
|Somente no ato  <br/> |![SFB com suporte com topologia MA, somente local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuários localizados em casas/caixas de correio: local  <br/> |O MA está em SFB no local.  <br/> Portanto, o servidor de autorização é ADFS.  <br/> Para obter detalhes de configuração, consulte [este artigo.](/microsoft-365/enterprise/hybrid-modern-auth-overview) <br/> |MFA (Windows desktop somente - clientes móveis não são suportados). Nenhum Exchange de integração.  <br/><p> **Não recomendamos essa abordagem. Confira aqui:** [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview)<p/> |

> [!IMPORTANT]
> É recomendável que o estado ma seja o mesmo entre Skype for Business e Exchange (e suas contrapartes online) para reduzir o número de prompts.

Topologias misturadas envolvem combinações de híbridos de domínio dividido SFB. Estas são as topologias misturadas atualmente suportadas:

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Misto 1  <br/> |![SFB suportado com topologia MA, Misto 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuários localizados em casas/caixas de correio: EXO e SFB  <br/> |O MA não está habilitado para SFB; sem recursos ma SFB disponíveis nesta topologia.  <br/> |Sem recursos ma para SFB.  <br/> |
|Misto 2  <br/> |![Ma suportado com topologia Mista S4B 2, SFBO mais MA trabalhando com EXCH on-prem.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuários localizados em casas/caixas de correio: EXCH e SFBO  <br/> |O MA está somente para SFBO. O servidor de autorização é o Azure AD para usuários que estão no SFBO, mas o AD para EXCH no local.  <br/> |MFA, CBA, CA/MAM com o Intune.\*  <br/> |
|Misto 3  <br/> |![MA com suporte com SFB, EXO com MA on, além de EXCH e SFB no local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuários localizados em casas/caixas de correio: EXO + SFB ou EXCH + SFB  <br/> |Sem recursos ma SFB disponíveis nesta topologia  <br/> |Sem recursos ma para SFB.  <br/> |
|Misto 4  <br/> |![MA com suporte com SFB, SFBO com MA on, além de EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuários localizados em casas/caixas de correio: EXCH +SFBO ou EXCH + SFB  <br/> |O MA está no SFBO, portanto, o servidor de autorização é o Azure AD para usuários que estão no SFBO. Os usuários in-prem no SFB e no EXO usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|Misto 5  <br/> |![Ma com suporte em SFB, EXO com MA e SFBO com MA e EXCH e SFB no local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuários localizados em casas/caixas de correio: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está no EXO e no SFBO, portanto, o servidor de autorização é o Azure AD para usuários que estão no SFBO; Os usuários in-prem no EXCH e no SFB usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|Misto 6  <br/> |![Em uma topologia Mista 6, a Autenticação Moderna está em todos os quatro locais possibile - a situtação ideal quando se trata de Modern Auth.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuários localizados em casas/caixas de correio: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está em todos os lugares, portanto, o servidor de autorização é o Azure AD para todos os usuários. (online e local)  <br/>  Confira as [https://aka.ms/ModernAuthOverview](/microsoft-365/enterprise/hybrid-modern-auth-overview) etapas de implantação. <br/> |MFA, CBA e CA/MAM (via Intune) para todos os usuários.  <br/> |

\*- O MFA inclui Windows desktop, MAC, iOS, dispositivos Android e Windows Telefones; O CBA inclui Windows desktop, iOS e dispositivos Android; CA/MAM com Intune, inclui dispositivos Android e iOS.

> [!IMPORTANT]
> É muito importante observar que os usuários podem ver vários **prompts** em alguns casos, principalmente quando o estado ma não é o mesmo em todos os recursos de servidor que os clientes podem precisar e solicitar, como é o caso de todas as versões das topologias misturadas.

> [!IMPORTANT]
> Observe também que, em alguns casos (Mixed 1, 3 e 5 especificamente), uma chave de registro [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) deve ser definida para a configuração adequada para clientes de área de trabalho Windows.