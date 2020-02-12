---
title: Requisitos de DNS para URLs simples no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumo: revise as considerações de URL simples neste tópico antes de implementar registros DNS para o Skype for Business Server.'
ms.openlocfilehash: 3296e3678d1d38f021b792a2362f61de66796d0f
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888470"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos de DNS para URLs simples no Skype for Business Server

**Resumo:** Examine as considerações de URL simples neste tópico antes de implementar registros de DNS para o Skype for Business Server.

URLs simples facilitam a União de reuniões para seus usuários e facilitam a obtenção de ferramentas administrativas do Skype for Business Server. URLs simples usam seu próprio domínio, que não deve corresponder a qualquer um dos domínios SIP que você definir. 

O Skype for Business Server dá suporte a estas três URLs simples: atender, discagem e administrador. Você é obrigado a configurar URLs simples para atender e discagem, e a URL simples de administrador é opcional. Os registros de sistema de nome de domínio (DNS) que você precisa para dar suporte a URLs simples dependem de como você definiu essas URLs simples e se deseja dar suporte à recuperação de desastres para URLs simples. 

## <a name="simple-url-scope"></a>Escopo de URL simples

Você pode configurar suas URLs simples para ter escopo global ou pode especificar diferentes URLs simples para cada site central em sua organização. Se tanto uma URL simples global quanto uma URL simples do site forem especificadas, a URL simples do site terá precedência. 

Na maioria dos casos, recomendamos que você defina URLs simples somente no nível global, de modo que a URL simples de um usuário não seja alterada se passar de um site para outro. A exceção seria organizações que precisam usar números de telefone diferentes para usuários de discagem em sites diferentes. Observe que, se você definir uma URL simples (como a URL simples de discagem) em um site para ser uma URL simples no nível do site, também deverá definir que outras URLs simples nesse site também sejam no nível do site.

Você pode definir URLs simples globais no construtor de topologias. Para definir uma URL simples no nível do site, use o cmdlet Set-CsSimpleURLConfiguration.

Definir uma URL simples também exigirá a configuração de um registro A e/ou AAAA na configuração do DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Regras de nomenclatura e validação de URL simples
<a name="BK_Valid"> </a>

O construtor de topologias e os cmdlets do Shell de gerenciamento do Skype for Business Server aplicam várias regras de validação para suas URLs simples. Você precisa definir URLs simples para atender e fazer chamadas, mas a configuração de um para administrador é opcional. Cada domínio SIP deve ter uma URL simples de reunião separada, mas você precisa apenas de uma URL simples de discagem e uma URL simples de administrador para toda a sua organização.

Cada URL simples em sua organização deve ter um nome exclusivo e não pode ser um prefixo de outra URL simples (por exemplo, não foi possível definir SfB2015.contoso.com/Meet como o seu URL simples e o SfB2015.contoso.com/Meet/Dialin como sua URL simples de discagem). Nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou de qualquer informação de https://FQDN:88/meet porta (por exemplo, não é permitido). Todas as URLs simples devem começar com o prefixo https://. 

As URLs simples podem conter apenas caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e ponto final (.). Se você usar outros caracteres, as URLs simples podem não funcionar como esperado.

## <a name="changing-simple-urls-after-deployment"></a>Alterar URLs simples após a implantação
<a name="BK_Valid"> </a>

Se você alterar uma URL simples após a implantação inicial, deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se a base de uma URL simples for alterada, você deverá alterar também os registros DNS e os certificados. Por exemplo, mudar de https://SfB2015.contoso.com/Meet para https://meet.contoso.com altera a URL base de SfB2015.contoso.com para Meet.contoso.com, portanto, você precisaria alterar os registros DNS e os certificados para se referirem ao Meet.contoso.com. Se você alterou a URL simples https://SfB2015.contoso.com/Meet de https://SfB2015.contoso.com/Meetingspara, a URL base de SfB2015.contoso.com permanece a mesma, portanto, não é necessária nenhuma alteração de DNS ou certificado.

No entanto, sempre que você alterar um nome de URL simples, você deve executar **Enable-CsComputer** em cada director e servidor front-end para registrar a alteração.

## <a name="naming-examples-for-simple-urls"></a>Exemplos de nomenclatura para URLs simples
<a name="BK_Valid"> </a>

Há três opções recomendadas para nomear suas URLs simples. Qual opção você escolhe tem implicações para a maneira como configurar seus registros DNS A e certificados que dão suporte a URLs simples. Em cada opção, você deve configurar uma URL simples de reunião para cada domínio SIP em sua organização. 

Você sempre precisa de apenas uma URL simples em toda a sua organização para discagem e outra para o administrador, independentemente de quantos domínios SIP você tem.

Na opção 1, crie um novo nome de domínio SIP para cada URL simples.

Se você usar essa opção, precisará de um registro DNS A separado para cada URL simples, e cada uma delas atenderá à URL simples deve ser nomeada em seus certificados.

**Opção de nomeação de URL simples 1**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Atendimento  <br/>          | https://meet.contoso.com, https://meet.fabrikam.come assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Locatário  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Com a opção 2, as URLs simples são baseadas no nome de domínio SfB2015.contoso.com. Portanto, você precisa apenas de um registro de DNS que habilite todos os três tipos de URLs simples. Esse registro DNS faz referência a SfB2015.contoso.com. Além disso, você ainda precisa de registros DNS A separados para outros domínios SIP em sua organização. 

**Opção de nomeação de URL simples 2**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Atendimento  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meete assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Locatário  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

A opção 3 será mais útil se você tiver muitos domínios SIP e quiser que eles tenham URLs simples de reunião e desejem minimizar o registro DNS e os requisitos de certificado para essas URLs simples. 

**Opção de nomeação de URL simples 3**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Atendimento  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Discagem  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Locatário  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opção de recuperação de desastres para URLs simples
<a name="BK_Valid"> </a>

Se você tiver vários sites que contenham pools de front-end e o seu provedor de DNS oferecer suporte a GeoDNS, você poderá configurar seus registros DNS para URLs simples para dar suporte à recuperação de desastres, para que a funcionalidade de URL simples continue mesmo que um pool de front-end inteiro seja desligado. Este recurso de recuperação de desastres dá suporte a URLs simples e de reunião discada.

Para configurar isso, crie dois endereços do GeoDNS. Cada endereço tem dois registros DNS A ou CNAME que são resolvidos para dois pools que são emparelhados para fins de recuperação de desastres. Um endereço GeoDNS é usado para acesso interno e é resolvido para o FQDN da Web interna ou o endereço IP do balanceador de carga para os dois pools. O outro endereço GeoDNS é usado para acesso externo e resolve para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools. Veja a seguir um exemplo de URL simples de reunião, usando os FQDNs dos grupos. 

```console
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```console
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Em seguida, crie registros CNAME que resolvem sua URL simples de reunião (como meet.contoso.com) para os dois endereços GeoDNS.

> [!NOTE]
> Se a sua rede usa hairpinning (direcionar todo o tráfego de URL simples por meio do link externo, incluindo o tráfego que vem de dentro da sua organização), você pode apenas configurar o endereço de GeoDNS externo e resolver o seu encontro URL simples para apenas isso Endereço externo.

Ao usar esse método, você pode configurar cada endereço do GeoDNS para usar um método de rodízio para distribuir solicitações para os dois pools ou para se conectar principalmente a um pool (como o pool localizado geograficamente) e usar o outro pool somente em caso de falha na conectividade. 

Você pode configurar a mesma configuração para a URL simples de discagem. Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo `dialin` para `meet` os registros DNS. Para a URL simples do administrador, use uma das três opções listadas anteriormente nesta seção.

Depois que essa configuração é configurada, você deve usar um aplicativo de monitoramento para configurar o monitoramento HTTP para observar falhas. Para acesso externo, monitor para ter certeza de que HTTPS Obtém lyncdiscover.<sipdomain> as solicitações para o FQDN da Web externa ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidas. Por exemplo, as seguintes solicitações não devem conter cabeçalho **Accept** e devem retornar **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para acesso interno, você deve monitorar a porta 5061 no FQDN da Web interno ou o endereço IP do balanceador de carga para os dois pools. Se alguma falha de conectividade for detectada, o VIP para esses pools deverá fechar as portas 80, 443 e 4443.


