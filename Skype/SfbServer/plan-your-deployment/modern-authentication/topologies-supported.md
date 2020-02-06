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
description: Este artigo lista as topologias online e locais que são compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança aplicáveis a cada topologia.
ms.openlocfilehash: 2eb043768c46406696b32da5dfb84e2358a30749
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815819"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Skype for Business topologies supported with Modern Authentication
 
Este artigo lista as topologias online e locais que são compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança aplicáveis a cada topologia.
  
## <a name="modern-authentication-in-skype-for-business"></a>Autenticação moderna no Skype for Business

O Skype for Business pode aproveitar as vantagens de segurança da autenticação moderna. Como o Skype for Business trabalha em estreita colaboração com o Exchange, o comportamento de logon que os usuários do cliente Skype for Business verão também será efetuado pelo status da autenticação moderna do Exchange. Isso também será aplicável caso você tenha um híbrido de domínio dividido do Skype for Business. Há várias partes se movendo, mas o objetivo aqui é uma lista de topologias compatíveis fácil de visualizar.
  
Se considerarmos o Skype for Business, o Skype for Business Online, o Exchange Server e o Exchange Online, quais topologias são compatíveis com a autenticação moderna?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologias de autenticação moderna compatíveis com o Skype for Business

Há potencialmente dois aplicativos de servidor e duas cargas de trabalho do Office 365 envolvidos com as topologias do Skype for Business utilizadas pela autenticação moderna.
  
- Skype for Business Server (RECOR 5) local
    
- Skype for Business Online (SFBO)
    
- Exchange Server local
    
- Exchange Server Online (EXO)
    
Outra parte importante da autenticação moderna é saber onde acontecerá a autenticação (authN) e a autorização (authZ) dos usuários. As duas opções são:
  
- Azure AD, online no Microsoft Cloud
    
- Active Directory Federation Server (ADFS) local
    
Então, ele se parece um pouco assim, com EXO e SFBO na nuvem com o Azure AD e Exchange Server (EXCH) e o Skype for Business Server (SFB) local.
  
![Um exemplo de todos os aplicativos (Exchange e Skype for Business) e cargas de trabalho (EXO e SFBO), e ambos os servidores de autorização (ADFS e evoSTS) que podem ser envolvidos ao ativar o MA.](../../media/18a3b451-1e64-40fc-b47f-7ce9587814bb.PNG)
  
Aqui estão as topologias compatíveis. Tenha em mente a explicação dos elementos gráficos:
  
- Se estiver esmaecido ou cinza, o ícone não é utilizado nesse cenário.
    
- EXO é o Exchange Online.
    
- SFBO é o Skype for Business Online.
    
- EXCH é o Exchange local.
    
- SFB é o Skype for Business local.
    
- Os servidores de autorização são representados por triângulos. Por exemplo, o Azure AD é um triângulo com uma nuvem atrás.
    
- As setas apontam para o servidor de autorização que será usado quando os clientes tentarem alcançar o recurso do servidor especificado.
    
Primeiro, vamos tratar da autorização moderna com o Skype for Business em topologias apenas locais e apenas na nuvem.
  
> [!IMPORTANT]
> Está pronto para configurar a autenticação moderna no Skype for Business Online? [Aqui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)estão as etapas para habilitar esse recurso. 
  
|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Compatível   <br/> |
|:-----|:-----|:-----|:-----|
|Somente na nuvem  <br/> |![SFB compatível com a topologia do MA, somente na nuvem.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuários hospedados/caixas de correio localizadas: Online   <br/> |A autenticação moderna está ativada tanto para o EXO quanto para o SFBO.  <br/> Portanto, o servidor de autorização é o Azure AD.  <br/> |Autenticação multifatorial (MFA), Autenticação baseada no certificado do cliente (CBA), Acesso condicional (CA)/Gerenciamento de aplicativo móvel (MAM) com o Intune. \*  <br/> |
|Somente local  <br/> |![Compatível com SFB com topologia MA somente local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuários hospedados/caixas de correio localizadas: no local  <br/> |A autenticação moderna está ativada para o SFB local.  <br/> Portanto, o servidor de autorização é o ADFS.  <br/> Para obter detalhes de configuração, confira [Este artigo.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA (somente para o Windows Desktop - os clientes móveis não são compatíveis). Nenhum recurso de integração do Exchange.  <br/><p> **Não recomendamos essa abordagem. **Acesse:[https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview)<p/> |
   
> [!IMPORTANT]
> Recomenda-se que o estado da autenticação moderna seja o mesmo no Skype for Business e no Exchange (e suas contrapartes online) para a redução do número de prompts. 
  
As topologias mistas envolvem combinações de híbridos de domínio dividido do SFB. Estas são as topologias mistas compatíveis no momento:
  
|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Compatível   <br/> |
|:-----|:-----|:-----|:-----|
|Mista 1  <br/> |![SFB com suporte com topologia MA, misturada 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO e SFB  <br/> |A autenticação moderna não está habilitada para o SFB; nenhum recurso de autenticação moderna do SFB disponível nesta topologia.  <br/> |Nenhum recurso de autenticação moderna para o SFB.  <br/> |
|Mista 2  <br/> |![MA com suporte com S4B Mixed Topology 2, SFBO Plus MA trabalhando com o EXCH local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH e SFBO  <br/> |A autenticação moderna está ativada somente para o SFB. O servidor de autorização é o Azure AD para usuários hospedados no SFBO, mas AD para EXCH no local.  <br/> |MFA, CBA, CA/MAM com o Intune.\*  <br/> |
|Mista 3  <br/> |![MA compatível com o SFB, o EXO com o MA ligado, além do EXCH e do SFB no local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFB ou EXCH + SFB  <br/> |Nenhum recurso de autenticação moderna do SFB disponível nesta topologia  <br/> |Nenhum recurso de autenticação moderna para o SFB.  <br/> |
|Mista 4  <br/> |![MA compatível com SFB, SFBO com MA on, Plus EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH +SFBO ou EXCH + SFB  <br/> |A autenticação moderna está ativada para o SFBO, portanto, o servidor de autorização é o Azure AD para os usuários hospedados no SFBO. Usuários locais no SFB e EXO usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|Mista 5  <br/> |![MA (MA) compatível no SFB, EXO com MA e SFBO com MA, e EXCH e SFB local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está ativado no EXO e no SFBO, portanto, o servidor de autorização é o Azure AD para usuários hospedados no SFBO; usuários locais no EXCH e SFB usam o AD.  <br/> |MFA, CBA, CA/MAM com o Intune somente para usuários online.\*  <br/> |
|6 misturado  <br/> |![Em uma topologia mista de 6, a autenticação moderna está ativada nos quatro locais do possibile-o situtation ideal quando chega à autenticação moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |O MA está em todos os lugares, portanto, o servidor de autorização é o Azure AD para todos os usuários. (online e local)  <br/>  Confira [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) as etapas de implantação. <br/> |MFA, CBA e CA/MAM (via Intune) para todos os usuários.  <br/> |
   
\*-O MFA inclui área de trabalho do Windows, MAC, iOS, dispositivos Android e Windows phones; O CBA inclui a área de trabalho do Windows, dispositivos iOS e Android; CA/MAM com o Intune, inclui dispositivos Android e iOS. 
  
> [!IMPORTANT]
> É muito importante observar que os usuários podem ver **vários prompts ** em alguns casos, particularmente onde o estado da autenticação moderna não é o mesmo em todos os recursos do servidor que os clientes podem precisar e solicitar. É o caso com todas as versões das topologias Mistas. 

> [!IMPORTANT]
> Observe também que, em alguns casos (1, 3 e 5 especificamente) uma chave do registro [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) deve ser definida para a configuração apropriada para clientes da área de trabalho do Windows.
  

