---
title: Requisitos de DNS para URLs simples no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3a3c9b22-892f-45a7-b05c-539d358a1a86
description: 'Resumo: Revise as considerações de URL simples neste tópico antes de implementar os registros DNS para Skype para Business Server.'
ms.openlocfilehash: 1fffb1303381797a800a235d3965fe387e4d8eb2
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878547"
---
# <a name="dns-requirements-for-simple-urls-in-skype-for-business-server"></a>Requisitos de DNS para URLs simples no Skype para Business Server

**Resumo:** Revise as considerações de URL simples neste tópico antes de implementar os registros DNS para Skype para Business Server.

URLs simples facilitam o ingresso de reuniões para seus usuários e conhecendo o Skype para ferramentas administrativas do Business Server mais fácil para os administradores. URLs simples usam seu próprio domínio, que não deverá corresponder a qualquer um dos domínios SIP que você define. 

Skype para Business Server suporta as seguintes três URLs simples: atenda, Dial-In e administrador. É necessário para configurar URLs simples de reunião e discagem e a URL simples de Admin é opcional. Os registros de sistema de nome de domínio (DNS) que você precisa oferecer suporte a URLs simples dependem de como você definiu essas URLs simples e se você deseja oferecer suporte a recuperação de desastres para URLs simples. 

## <a name="simple-url-scope"></a>Escopo de URL Simple

Você pode configurar seus URLs simples para têm escopo global ou, você pode especificar as URLs simples diferentes para cada site central em sua organização. Se uma URL simples global e uma URL simples do site forem especificados, a URL simples do site tem precedência. 

Na maioria dos casos, é recomendável que você defina URLs simples apenas no nível global, para que o URL reunir simples de um usuário não mude se movem de um site para outro. A exceção seria organizações que precisam usar números de telefone diferentes para usuários de discagem em sites diferentes. Observe que se você definir um URL simples (por exemplo, a discagem URL simples) em um site para ser uma URL simple de nível de site, você também deve definir as outras URLs simples nesse site a ser também o nível do site.

Você pode definir os URLs simples globais no construtor de topologia. Para definir uma URL simples no nível do site, use o cmdlet Set-CsSimpleURLConfiguration.

Definir uma URL simples também exigirá a configuração de um registro A e/ou AAAA na sua configuração DNS.

## <a name="simple-url-naming-and-validation-rules"></a>Regras de validação e nomeação de URL simples
<a name="BK_Valid"> </a>

Construtor de topologias e o Skype para cmdlets do Shell de gerenciamento do Business Server impor várias regras de validação para suas URLs simples. Você precisa configurar URLs simples para reunir e de discagem, mas a definição de um para administração é opcional. Cada domínio SIP deve ter uma URL reunir simples separado, mas você precisa apenas um URL simples de discagem e um administrador URL simples para toda sua organização.

Cada URL simples em sua organização deve ter um nome exclusivo e não pode ser um prefixo de URL simples outra (por exemplo, você poderia não definir SfB2015.contoso.com/Meet como sua URL reunir simples e SfB2015.contoso.com/Meet/Dialin como sua URL simple de discagem). Nomes de URL simples não podem conter o FQDN de qualquer um dos seus pools ou qualquer informação de porta (por exemplo, https://FQDN:88/meet não é permitido). Todas as URLs simples devem começar com o prefixo https://. 

URLs simples podem conter apenas caracteres alfanuméricos (ou seja, a-z, A-Z, 0-9 e o ponto (.). Se você usar outros caracteres, o simples URLs podem não funcionar conforme o esperado.

## <a name="changing-simple-urls-after-deployment"></a>Alterando URLs simples após a implantação
<a name="BK_Valid"> </a>

Se você alterar um URL simples após a implantação inicial, você deve estar ciente de como a alteração afeta seus registros DNS e certificados para URLs simples. Se a base de uma URL simples for alterado, você deve alterar os registros DNS e certificados também. Por exemplo, a alteração de https://SfB2015.contoso.com/Meet para https://meet.contoso.com altera a URL base do SfB2015.contoso.com para meet.contoso.com, portanto, seria necessário alterar os registros DNS e certificados para se referir a meet.contoso.com. Se você alterou a URL simples de https://SfB2015.contoso.com/Meet para https://SfB2015.contoso.com/Meetings, a URL base do SfB2015.contoso.com permanece o mesmo, portanto, não há DNS ou se forem necessárias alterações de certificado.

Sempre que você alterar um nome de URL simple, no entanto, você deve executar **Enable-CsComputer** em cada diretor e o servidor Front-End para registrar a alteração.

## <a name="naming-examples-for-simple-urls"></a>Exemplos de nomenclatura para URLs simples
<a name="BK_Valid"> </a>

Existem três opções recomendadas para Nomeando seus URLs simples. Opção que você escolher tem implicações em como você configurar registros DNS A e certificados que oferece suporte a URLs simples. Em cada opção, você deve configurar um URL reunir simples para cada domínio SIP em sua organização. 

Você sempre precisa de um URL simples em toda sua organização para Dial-in e um para administração, não importa quantos domínios SIP que você tenha.

Opção 1, você cria um novo nome de domínio SIP para cada URL simples.

Se você usar essa opção, você precisa de um registro DNS A separado para cada URL simples e cada URL reunir simples devem ser nomeado em seus certificados.

**Opção de nome de URL simples 1**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                    |
|:---------------------|:---------------------------------------------------------------------------------------------------------------------|
| Reunir  <br/>          | https://meet.contoso.com, https://meet.fabrikam.com, e assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | <https://dialin.contoso.com>  <br/>                                                                                  |
| Admin  <br/>         | <https://admin.contoso.com>  <br/>                                                                                   |

Com a opção 2, as URLs simples são baseados no nome de domínio SfB2015.contoso.com. Portanto, você precisa apenas um registro DNS A que permite que todos os três tipos de URLs simples. Esse registro DNS A referencia SfB2015.contoso.com. Além disso, você ainda precisa registros de DNS A separados para outros domínios SIP em sua organização. 

**Opção de nome de URL simples 2**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                                    |
|:---------------------|:-------------------------------------------------------------------------------------------------------------------------------------|
| Reunir  <br/>          | https://SfB2015.contoso.com/Meet, https://SfB2015.fabrikam.com/Meet, e assim por diante (um para cada domínio SIP em sua organização)  <br/> |
| Discagem  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                                          |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                                           |

Opção 3 é mais útil se você tiver vários domínios SIP, e você deseja que eles possuem atender a URLs simples separada, mas deseja minimizar os requisitos de certificado e de registro DNS para essas URLs simples. 

**Opção de nome de URL simples 3**


| **URL simples** <br/> | **Exemplo** <br/>                                                                                                      |
|:---------------------|:-----------------------------------------------------------------------------------------------------------------------|
| Reunir  <br/>          | <https://SfB2015.contoso.com/contosoSIPdomain/Meet>  <br/> <https://SfB2015.contoso.com/fabrikamSIPdomain/Meet>  <br/> |
| Discagem  <br/>       | <https://SfB2015.contoso.com/Dialin>  <br/>                                                                            |
| Admin  <br/>         | <https://SfB2015.contoso.com/Admin>  <br/>                                                                             |

## <a name="disaster-recovery-option-for-simple-urls"></a>Opção de recuperação de desastres para URLs simples
<a name="BK_Valid"> </a>

Se você tiver vários sites que contêm os pools de Front-End e seu provedor de DNS suporta GeoDNS, você pode configurar seus registros DNS para URLs simples dar suporte a recuperação de desastres, para que a funcionalidade de URL simples continuará, mesmo se um pool de Front-End inteiro cair. Oferece suporte a esse recurso de recuperação de desastres, a reunião e discagem URLs simples.

Para configurar isso, crie dois endereços de GeoDNS. Cada endereço tem dois registros DNS A ou CNAME que resolvem dois pools que são combinados juntos para fins de recuperação de desastres. Um endereço de GeoDNS é usado para acesso interno e resolve para o web internos FQDN ou carga balanceador endereço IP para os dois pools. O outro endereço GeoDNS é usado para acesso externo e resolve para o web externos FQDN ou carga balanceador endereço IP para os dois pools. O exemplo a seguir é um exemplo para a URL simples Meet, usando os FQDNs para os pools. 

```
Meet-int.geolb.contoso.com
     Pool1InternalWebFQDN.contoso.com
     Pool2InternalWebFQDN.contoso.com
```

```
Meet-ext.geolb.contoso.com
     Pool1ExternalWebFQDN.contoso.com
     Pool2ExternalWebFQDN.contoso.com
```

Em seguida, crie registros CNAME que decomponham sua URL simples Meet (como meet.contoso.com) para os dois endereços de GeoDNS.

> [!NOTE]
> Se a sua rede usa hairpinning (roteamento todo seu URL simples o tráfego através do link externo, incluindo o tráfego que vem de dentro da sua organização), em seguida, basta configurar o endereço de GeoDNS externo e resolver sua URL simples Meet apenas que endereço externo.

Quando você usa esse método, você pode configurar cada endereço de GeoDNS para usar um método de rodízio para distribuir as solicitações para os dois pools, ou para conectar-se principalmente para um pool (por exemplo, o pool localizado geograficamente mais próximos) e usar o outro pool apenas no caso de Falha de conectividade. 

Você pode configurar a mesma configuração para a URL simples Dial-In. Para fazer isso, crie registros adicionais, como aqueles no exemplo anterior, substituindo `dialin` para `meet` nos registros DNS. Para a URL simples Admin, use uma das três opções listadas anteriormente nesta seção.

Depois que essa configuração estiver configurada, você deve usar um aplicativo de monitoramento para configurar o monitoramento de HTTP de detecção de falhas. Para acesso externo, monitor para certificar-se de que lyncdiscover obter HTTPS.<sipdomain> solicitações para a endereço IP balanceador FQDN ou carga para os dois pools da web externos são bem-sucedidas. Por exemplo, as solicitações a seguir não deve conter qualquer cabeçalho **ACCEPT** e deve retornar **200 Okey**.

```
HTTPS GET Pool1ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
HTTPS GET Pool2ExternalWebFQDN.contoso.com/autodiscover/autodiscoverservice.svc/root
```

Para acesso interno, você deve monitorar a porta 5061 na web FQDN interna ou endereço IP do balanceador para os dois pools de carga. Se forem detectadas quaisquer falhas de conectividade, o VIP para estes pools deve fechar as portas 80, 443 e 4443.


