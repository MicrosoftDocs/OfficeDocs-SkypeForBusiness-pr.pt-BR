---
title: Requisitos dns para URLs simples em Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumo: revise as considerações de URL simples neste tópico antes de implementar registros DNS para Skype for Business Server.'
ms.openlocfilehash: d638ff2d3d1b89deaad90c054698692e70ffaae7
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60777911"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos dns para URLs simples em Skype for Business Server

**Resumo:** Revise as considerações de URL simples neste tópico antes de implementar registros DNS para Skype for Business Server.

As URLs simples facilitam a junção de reuniões para os usuários e facilitam a Skype for Business Server administrativas para administradores. As URLs simples usam seu próprio domínio, que não deve corresponder a nenhum dos domínios SIP definidos. 

Skype for Business Server dá suporte às três URLs simples a seguir: Meet, Dial-In e Admin. Você deve configurar URLs simples para Meet e Dial-In, e a URL simples de Administrador é opcional. Os registros de DNS (Sistema de Nomes de Domínio) necessários para dar suporte às URLs simples dependem de como elas foram definidas e de você deseja dar suporte à recuperação de desastre para URLs simples. 

## <a name="simple-url-scope"></a>Escopo de URL simples

Você pode configurar seus URLs simples para que tenham um escopo global ou você pode especificar URLs simples diferentes para cada site central na sua organização. Se tanto o URL simples global como o URL simples de site forem especificados, a preferência é do URL simples de site. 

Na maioria dos casos, recomendamos que você defina URLs simples apenas no nível global, para que a URL simples meet de um usuário não seja mudada se elas mudarem de um site para outro. A exceção seria para organizações que precisam usar números de telefone diferentes para os usuários de discagem em locais diferentes. Observe que se você definir um URL simples (como o URL simples Discar) em um site para que ele seja um site de nível de URL simples, você deve definir também outros URLs simples para que eles também estejam no nível de site de URL simples.

Você pode definir URLs simples globais no Construtor de Topologias. Para definir uma URL simples no nível do site, use Set-CsSimpleURLConfiguration cmdlet.

A definição de uma URL simples também exigirá a configuração de um registro A e/ou AAAA em sua configuração DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Regras simples de nomenis e validação de URL
<a name="BK_Valid"> </a>

O Construtor de Topologias e os cmdlets Skype for Business Server Shell de Gerenciamento impõem várias regras de validação para suas URLs simples. Será solicitado que você defina URLs simples para Reunir e Discar, mas para Admin será opcional. Cada domínio SIP deve ter um URL Reunir simples, mas você precisa somente de um URL Discar simples e um URL Admin simples para toda sua organização.

Cada URL simples em sua organização deve ter um nome exclusivo e não pode ser um prefixo de outra URL simples (por exemplo, você não pode definir como sua URL simples de Reunião e como sua URL simples `SfB2015.contoso.com/Meet` `SfB2015.contoso.com/Meet/Dialin` de Dialin). Nomes de URL simples não podem conter o FQDN de qualquer um de seus pools ou qualquer informação de porta (por exemplo, https://FQDN:88/meet não é permitido). Todas as URLs simples devem começar com o prefixo https://. 

URLs simples podem conter somente caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e o ponto (.). Se você utilizar outros caracteres, o URL simples pode não funcionar como esperado.

## <a name="changing-simple-urls-after-deployment"></a>Alterar URLs simples após a implantação
<a name="BK_Valid"> </a>

Se você alterar uma URL simples após a implantação inicial, esteja ciente de quais alterações impactarão nos seus registros DNS e certificados para as URLs simples. Se a alteração impactar a base de uma URL simples, você precisará alterar os registros de DNS e certificados também. Por exemplo, mudar de para alterar a URL base de para , portanto, você precisaria alterar os registros `https://SfB2015.contoso.com/Meet` `https://meet.contoso.com` DNS e `SfB2015.contoso.com` `meet.contoso.com` certificados para se referir a `meet.contoso.com` . Se você alterou a URL simples de para , a URL base de permanece a mesma, para que `https://SfB2015.contoso.com/Meet` nenhuma alteração de DNS ou certificado seja `https://SfB2015.contoso.com/Meetings` `SfB2015.contoso.com` necessária.

Sempre que você alterar um nome de URL simples, no entanto, você deve executar **Enable-CsComputer** em cada Diretor e Servidor front-end para registrar a alteração.

## <a name="naming-examples-for-simple-urls"></a>Nomenis para URLs simples
<a name="BK_Valid"> </a>

Existem três opções recomendadas para nomear seus URLs simples. A opção escolhida implica em como configurar seus registros A de DNS e os certificados que suportam URLs simples. Em cada opção, você deve configurar um URL de Reunião simples para cada domínio SIP na sua organização. 

Você sempre precisa de um URL simples para toda sua organização para Discar e um para Administração, não importa quantos domínios SIP você tenha.

Na Opção 1, você cria um novo nome de domínio SIP para cada URL simples.

Se usar esta opção, você precisará de um registro A de DNS separado para cada URL simples e cada URL Reunir simples deve ser nomeado em seus certificados.

**Opção 1 de nome de URL simples**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://meet.contoso.com`, `https://meet.fabrikam.com` e assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | `<https://dialin.contoso.com>`  <br/>                                                                                  |
| Administrador  <br/>         | `<https://admin.contoso.com>`  <br/>                                                                                   |

Com a Opção 2, AS URLs simples se baseiam no nome de domínio `SfB2015.contoso.com` . Por isso, você precisará somente de um registro A de DNS que permita todos os três tipos de URL simples. Este registro DNS A faz `SfB2015.contoso.com` referência. além disso, você ainda precisa separar os registros A de DNS para os outros domínios SIP da sua organização. 

**Opção 2 de nome de URL simples**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `https://SfB2015.contoso.com/Meet`, `https://SfB2015.fabrikam.com/Meet` e assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                                          |
| Administrador  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                                           |

A opção 3 é mais útil se você tiver muitos domínios SIP e desejar que eles tenham URLs Reunir separadas, mas desejar minimizar o registro de DNS e os requisitos de certificação para esses URLs simples. 

**Opção 3 de nome de URL simples**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Meet  <br/>          | `<https://SfB2015.contoso.com/contosoSIPdomain/Meet>`  <br/> `<https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>`  <br/> |
| Discagem  <br/>       | `<https://SfB2015.contoso.com/Dialin>`  <br/>                                                                            |
| Administrador  <br/>         | `<https://SfB2015.contoso.com/Admin>`  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opção recuperação de desastres para URLs simples
<a name="BK_Valid"> </a>

Se você tiver vários sites que contêm pools de Front-End e seu provedor DNS der suporte a GeoDNS, você poderá configurar seus registros DNS para URLs simples para dar suporte à recuperação de desastres, para que a funcionalidade url simples continue mesmo se um pool de Front-End inteiro ficar para baixo. Este recurso de recuperação de desastres dá suporte às URLs simples Meet e Dial-In.

Para fazer essa configuração, crie dois endereços de GeoDNS. Cada endereço contém dois registros DNS A ou CNAME que são decompostos em dois pools que são unidos para fins de recuperação de desastres. Um endereço de GeoDNS é usado para acesso interno e é decomposto no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. O outro endereço GeoDNS é usado para acesso externo e é decomposto no FQDN da Web externo ou endereço IP do balanceador de carga dos dois pools. Veja a seguir um exemplo da URL simples Meet, usando os FQDNs dos pools: 

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

Em seguida, crie registros CNAME que resolvam a URL simples meet (como `meet.contoso.com` ) para os dois endereços GeoDNS.

> [!NOTE]
> Se sua rede usar grampeamento (roteamento de todo o tráfego de URLs simples pelos links externos, inclusive o tráfego que vem de dentro de sua organização), será possível simplesmente configurar os endereços de GeoDNS externos e decompor sua URL simples Meet apenas nesses endereços externos.

Quando esse método é usado, é possível configurar cada endereço de GeoDNS para usar um método de round robin e distribuir solicitações nos dois pools ou para fazer a conexão principalmente com um pool (como o pool localizado geograficamente mais perto) e usar o outro pool apenas em caso de falhas de conectividade. 

Você pode definir a mesma configuração para a URL simples Dial-In. Para fazer isso, crie registros adicionais como os do exemplo anterior, substituindo  `dialin` `meet` nos registros DNS. Para a URL simples Admin, use uma das três opções listadas anteriormente nesta seção.

Depois que esta configuração é definida, é preciso usar um aplicativo de monitoramento para definir que o monitoramento de HTTP rastreie as falhas. Para acesso externo, monitore para garantir que HTTPS GET lyncdiscover.<sipdomain> as solicitações para o FQDN da Web externo ou o endereço IP do balanceador de carga para os dois pools são bem-sucedidas. Por exemplo, as solicitações a seguir não devem conter nenhum cabeçalho **ACCEPT** e devem retornar **200 OK**.

```console
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para acesso interno, é preciso monitorar a porta 5061 no FQDN da Web interno ou endereço IP do balanceador de carga dos dois pools. Se alguma falha de conectividade for detectada, o VIP para esses pools deverá fechar as portas 80, 443 e 4443.


