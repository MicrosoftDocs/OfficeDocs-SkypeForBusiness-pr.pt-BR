---
title: Topologias do Skype for Business compatíveis com a autenticação moderna
ms.author: tracyp
author: MSFTTracyP
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: tracyp
ms.assetid: 258430b0-574a-47fb-90b7-54ee8996b2ec
description: Este artigo lista as topologias online e locais que são compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança aplicáveis a cada topologia.
ms.openlocfilehash: cc849dc1df0f4bf97bb362449ef1ded58596cb91
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21001796"
---
# <a name="skype-for-business-topologies-supported-with-modern-authentication"></a>Topologias do Skype for Business compatíveis com a autenticação moderna
 
Este artigo lista as topologias online e locais que são compatíveis com a autenticação moderna no Skype for Business, bem como os recursos de segurança aplicáveis a cada topologia.
  
## <a name="modern-authentication-in-skype-for-business"></a>Autenticação moderna no Skype for Business

O Skype for Business pode aproveitar as vantagens de segurança da autenticação moderna. Como o Skype for Business trabalha em estreita colaboração com o Exchange, o comportamento de logon que os usuários do cliente Skype for Business verão também será efetuado pelo status da autenticação moderna do Exchange. Isso também será aplicável caso você tenha um híbrido de domínio dividido do Skype for Business. Há várias partes se movendo, mas o objetivo aqui é uma lista de topologias compatíveis fácil de visualizar.
  
Se considerarmos o Skype for Business, o Skype for Business Online, o Exchange Server e o Exchange Online, quais topologias são compatíveis com a autenticação moderna?
  
<!--  > [!TIP] > Not sure what Modern Authentication even is? No worries.  This Skype for Business article  4e6a99cd-7859-4062-8a30-5ac79ba36b52  explains it in the first paragraphs. --> 
  
### <a name="supported-ma-topologies-in-skype-for-business"></a>Topologias de autenticação moderna compatíveis com o Skype for Business

Há potencialmente dois aplicativos de servidor e duas cargas de trabalho do Office 365 envolvidos com as topologias do Skype for Business utilizadas pela autenticação moderna.
  
- Skype para negócios (5 CU) de servidor local
    
- Skype for Business Online (SFBO)
    
- Exchange Server local
    
- Exchange Server Online (EXO)
    
Outra parte importante da autenticação moderna é saber onde acontecerá a autenticação (authN) e a autorização (authZ) dos usuários. As duas opções são:
  
- Azure AD, online no Microsoft Cloud
    
- Active Directory Federation Server (ADFS) local
    
Para que ele um pouco parecida com esta, com EXO e SFBO na nuvem com o Azure AD e o Exchange Server (EXCH) e Skype para negócios o servidor (SFB) prem.
  
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
> Está pronto para configurar a autenticação moderna no Skype for Business Online? As etapas para habilitar esse recurso são adequadas [aqui](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx). 
  
|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Compatível  <br/> |
|:-----|:-----|:-----|:-----|
|Somente na nuvem  <br/> |![SFB compatível com topologia MA, somente Nuvem.](../../media/4d19b47f-8257-4a6f-9dab-0755206f7c52.PNG)Usuários hospedados/caixas de correio localizadas: Online   <br/> |A autenticação moderna está ativada tanto para o EXO quanto para o SFBO.  <br/> Portanto, o servidor de autorização é o Azure AD.  <br/> |A autenticação multifator (MFA), certificado de cliente com base em autenticação (CBA), acesso condicional (CA) / gerenciamento do aplicativo Mobile (MAM) com Intune. \*  <br/> |
|Somente local  <br/> |![SFB compatível com topologia MA, somente local.](../../media/9773e9a5-7cd6-41ef-940b-c4386c9fce20.PNG)Usuários hospedados/caixas de correio localizadas: no local  <br/> |A autenticação moderna está ativada para o SFB local.  <br/> Portanto, o servidor de autorização é o ADFS.  <br/> Para obter detalhes de configuração, consulte [neste artigo.](https://technet.microsoft.com/en-us/library/mt710548.aspx) <br/> |MFA (somente para o Windows Desktop - os clientes móveis não são compatíveis). Nenhum recurso de integração do Exchange.  <br/> |
   
> [!IMPORTANT]
> Recomenda-se que o estado da autenticação moderna seja o mesmo no Skype for Business e no Exchange (e suas contrapartes online) para a redução do número de prompts. 
  
As topologias mistas envolvem combinações de híbridos de domínio dividido do SFB. Estas são as topologias mistas compatíveis no momento:
  
|Nome da topologia  <br/> |Exemplo  <br/> |Descrição  <br/> |Compatível   <br/> |
|:-----|:-----|:-----|:-----|
|Mista 1  <br/> |![SFB compatível com topologia MA, Mista 1 (EXO + SFB).](../../media/7b2e607a-c83a-4bb3-9b48-a43566516129.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO e SFB  <br/> |A autenticação moderna não está habilitada para o SFB; nenhum recurso de autenticação moderna do SFB disponível nesta topologia.  <br/> |Nenhum recurso de autenticação moderna para o SFB.  <br/> |
|Mista 2  <br/> |![MA compatível com S4B Topologia mista 2, SFBO mais MA funcionando com EXCH local.](../../media/247a985d-39cd-4c16-a19e-b8b65207d82e.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH e SFBO  <br/> |MA está ativado para SFBO somente. O servidor de autorização é Azure AD para usuários hospedados no SFBO, mas AD para EXCH local.  <br/> |MFA, CBA CA/MAM com Intune.\*  <br/> |
|Mista 3  <br/> |![MA compatível com SFB, EXO com MA ativado, mais EXCH e SFB local.](../../media/772dc261-c041-4a96-90d0-fd0b5124decf.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFB ou EXCH + SFB  <br/> |Nenhum recurso de autenticação moderna do SFB disponível nesta topologia  <br/> |Nenhum recurso de autenticação moderna para o SFB.  <br/> |
|Mista 4  <br/> |![MA compatível com SFB, SFBO com MA ativado, mais EXCH e SFB.](../../media/8971bfaf-961f-476c-b16e-5418d1fa0a6d.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXCH +SFBO ou EXCH + SFB   <br/> |MA destina-se em SFBO, portanto, o servidor de autorização é Azure AD para usuários hospedados no SFBO. Os usuários em prem SFB e EXO usam AD.  <br/> |MFA, CBA CA/MAM com Intune online somente para usuários.\*  <br/> |
|Mista 5  <br/> |![MA compatível no SFB, EXO com MA e SFBO com MA, e EXCH e SFB local.](../../media/ecc366cf-1a7b-4ad1-bf8e-57111b8ad94f.PNG)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA é no EXO e SFBO, portanto, que o servidor de autorização é Azure AD para usuários hospedados no SFBO; os usuários em prem EXCH e SFB usam AD.  <br/> |MFA, CBA CA/MAM com Intune online somente para usuários.\*  <br/> |
|6 misto  <br/> |![Em uma topologia Mista 6, a Autenticação Moderna está em todos os quatro locais possíveis. Essa é a situação ideal para a Autenticação Moderna.](../../media/8de21756-9152-466d-a706-58b258e2271c.png)           <br/> Usuários hospedados/caixas de correio localizadas: EXO + SFBO, EXO + SFB, EXCH + SFBO ou EXCH + SFB  <br/> |MA está em todos os lugares, portanto, o servidor de autorização é Azure AD para todos os usuários. (online e no local)  <br/>  Consulte [https://aka.ms/ModernAuthOverview](https://aka.ms/ModernAuthOverview) para as etapas de implantação. <br/> |MFA, CBA e CA/MAM (via Intune) para todos os usuários.  <br/> |
   
\*-MFA inclui a área de trabalho do Windows, MAC, iOS, dispositivos com Android e Windows Phones; CBA inclui a área de trabalho do Windows, iOS e dispositivos com Android; Autoridade de certificação/MAM com Intune, inclui dispositivos Android e iOS. 
  
> [!IMPORTANT]
> É muito importante observar que os usuários podem ver **vários prompts ** em alguns casos, particularmente onde o estado da autenticação moderna não é o mesmo em todos os recursos do servidor que os clientes podem precisar e solicitar. É o caso com todas as versões das topologias Mistas.

> [!IMPORTANT]
> Observe também que, em alguns casos (especificamente misto 1, 3 e 5) uma chave de registro [AllowADALForNonLynIndependentOfLync](https://support.microsoft.com/en-us/help/3082803/info-about-the-allowadalfornonlyncindependentoflync-setting-in-skype-for-business,-lync-2013,-and-exchange-online) deve ser definida para a configuração correta para clientes de área de trabalho do Windows.
  

