---
title: Topologias do Skype for Business compatíveis com a Autenticação Moderna
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
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Este artigo lista quais topologias online e locais têm suporte com a Autenticação Moderna no Skype for Business, bem como os recursos de segurança que se aplicam a cada topologia.
ms.openlocfilehash: b7582b6f77a3286a2b245b4b390efee7bbef62c1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810091"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologias do Skype for Business compatíveis com a Autenticação Moderna

Este artigo lista quais topologias online e locais têm suporte com a Autenticação Moderna no Skype for Business, bem como os recursos de segurança que se aplicam a cada topologia.

## <a name="modern-authentication-in-skype-for-business"></a>Autenticação moderna no Skype for Business

O Skype for Business pode aproveitar as vantagens de segurança da Autenticação Moderna. Como o Skype for Business funciona em estreita proximidade com o Exchange, o comportamento de logon que os usuários do cliente Skype for Business verão também será afetado pelo status de MA do Exchange. Isso também se aplicará se você tiver um híbrido de domínio dividido do Skype for Business. Há muitas partes móveis, mas o objetivo aqui é uma lista fácil de visualizar de topologias com suporte.

Considerando o Skype for Business, o Skype for Business Online, o Exchange Server e o Exchange Online, quais topologias são suportadas com a ma?

<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. -->

### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologias de MA suportadas no Skype for Business

Há potencialmente dois aplicativos de servidor, e duas cargas de trabalho do Microsoft 365 ou Office 365, envolvidas com topologias do Skype for Business usadas pelo MA.

- Skype for Business Server (CU 5) local

- Skype for Business Online (SFBO)

- Exchange Server local

- Exchange Server Online (EXO)

Outra parte importante da autenticação é saber onde ocorrerá a autenticação (authN) e a autorização (authZ) dos usuários. As duas opções são:

- Azure AD, online no Microsoft Cloud

- Servidor de Federação do Active Directory (ADFS) local

Portanto, ele tem uma aparência um pouco assim, com EXO e SFBO na nuvem com o Azure AD, e Exchange Server (EXCH) e Skype for Business Server (SFB) no local.

![Um exemplo de todos os aplicativos (Exchange e Skype for Business) e cargas de trabalho (EXO e SFBO), e ambos os servidores de autorização (ADFS e evoSTS) que podem ser envolvidos ao ligar o MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)

Aqui estão as topologias com suporte. Anote a chave dos elementos gráficos:

- Se o ícone estiver esmaecida ou cinza, ele não será usado no cenário.

- EXO é o Exchange Online.

- O SFBO é o Skype for Business Online.

- EXCH é o Exchange local.

- SFB é o Skype for Business local.

- A autorização de servidores é representada por triângulos, por exemplo, o Azure AD é um triângulo com uma nuvem atrás dele.

- As setas apontam para o servidor de autorização que será usado quando os clientes tentarem alcançar o recurso de servidor especificado.

Primeiro, vamos cobrir a ma com o Skype for Business em topologias somente local ou somente na nuvem.

> [!IMPORTANT]
> Você está pronto para configurar a autenticação moderna no Skype for Business Online? As etapas para habilitar esse recurso [estão](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)aqui.

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Somente na nuvem  <br/> |![SFB com suporte com topologia ma, somente nuvem.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuários localizados/caixas de correio localizadas: Online  <br/> |A ma está 1 para EXO e SFBO.  <br/> Portanto, o servidor de autorização é o Azure AD.  <br/> |Autenticação multifacional (MFA), autenticação baseada em certificado de cliente (CBA), Acesso Condicional (CA)/Gerenciamento de Aplicativo Móvel (MAM) com o Intune. \*  <br/> |
|Somente no prem  <br/> |![SFB com suporte com topologia ma, somente no local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuários localizados/caixas de correio localizadas: no local  <br/> |A ma está 1.000 para SFB no local.  <br/> Portanto, o servidor de autorização é o ADFS.  <br/> Para obter detalhes de configuração, consulte [este artigo.](https://technet.microsoft.com/library/mt710548.aspx) <br/> |MFA (somente para Área de Trabalho do Windows - não há suporte para clientes móveis). Nenhum recursos de integração do Exchange.  <br/><p> **Não recomendamos essa abordagem. Confira aqui:**[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |

> [!IMPORTANT]
> É recomendável que o estado de MA seja o mesmo no Skype for Business e no Exchange (e suas contrapartes online) para reduzir o número de prompts.

Topologias mistas envolvem combinações de híbridos de domínio dividido do SFB. Estas são as topologias mistas atualmente com suporte:

|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Com suporte  <br/> |
|:-----|:-----|:-----|:-----|
|Misto 1  <br/> |![SFB com suporte com topologia ma, Misto 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuários localizados/caixas de correio localizadas: EXO e SFB  <br/> |A ma não está habilitada para SFB; nenhum recursos de ma SFB disponíveis nesta topologia.  <br/> |Nenhum recursos de ma para SFB.  <br/> |
|Misto 2  <br/> |![Ma com suporte com topologia Mista S4B 2, SFBO mais MA trabalhando com EXCH no lugar.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuários localizados/caixas de correio localizadas: EXCH e SFBO  <br/> |A ma está 1.000 somente no SFBO. O servidor de autorização é o Azure AD para usuários que estão no SFBO, mas o AD para EXCH no local.  <br/> |MFA, CBA, CA/MAM com Intune.\*  <br/> |
|Misto 3  <br/> |![Ma com suporte com SFB, EXO com MA on, além de EXCH e SFB no local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuários localizados/caixas de correio localizadas: EXO + SFB ou EXCH + SFB  <br/> |Não há recursos de ma SFB disponíveis nesta topologia  <br/> |Nenhum recursos de ma para SFB.  <br/> |
|Misto 4  <br/> |![Ma com suporte com SFB, SFBO com MA on, além de EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuários localizados/caixas de correio localizadas: EXCH +SFBO ou EXCH + SFB  <br/> |A ma está logon no SFBO, portanto, o servidor de autorização é o Azure AD para usuários que estão no SFBO. Os usuários no lugar no SFB e no EXO usam o AD.  <br/> |MFA, CBA, CA/MAM com Intune somente para usuários online.\*  <br/> |
|Misto 5  <br/> |![Ma com suporte no SFB, EXO com MA e SFBO com MA e EXCH e SFB no local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuários localizados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |A ma está no EXO e no SFBO, portanto, o servidor de autorização é o Azure AD para usuários que estão no SFBO; Os usuários no lugar do EXCH e do SFB usam o AD.  <br/> |MFA, CBA, CA/MAM com Intune somente para usuários online.\*  <br/> |
|Misto 6  <br/> |![Em uma topologia mista 6, a Autenticação Moderna está em todos os quatro locais possibile - a opção ideal quando se trata de Autenticação Moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuários localizados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |A ma está em todos os lugares, portanto, o servidor de autorização é o Azure AD para todos os usuários. (online e local)  <br/>  Consulte as [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) etapas de implantação. <br/> |MFA, CBA e CA/MAM (via Intune) para todos os usuários.  <br/> |

\* - A MFA inclui Windows Desktop, MAC, iOS, dispositivos Android e Windows Phones; O CBA inclui dispositivos Windows Desktop, iOS e Android; CA/MAM com Intune, inclui dispositivos Android e iOS.

> [!IMPORTANT]
> É muito importante observar que os usuários podem ver vários **prompts** em alguns casos, principalmente quando o estado de ma não é o mesmo em todos os recursos de servidor que os clientes podem precisar e solicitar, como é o caso com todas as versões das topologias mistas.

> [!IMPORTANT]
> Observe também que, em alguns casos (especificamente, 1, 3 e 5), uma chave de registro [AllowADALForNonLyncIndependentOfLync](https://support.microsoft.com/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) deve ser definida para a configuração adequada para clientes da área de trabalho do Windows.


