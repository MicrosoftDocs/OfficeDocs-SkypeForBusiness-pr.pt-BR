---
title: Infraestrutura de chave pública do Skype for Business Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype para Business Server 2015 depende de certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as funções de servidor diferente. O Windows Server 2012 R2, o Windows Server 2012, o Windows Server 2008 R2 e a ferramenta infraestrutura de chave pública (PKI) do Windows Server 2008 fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
ms.openlocfilehash: 8987eb0919f7fd7dcebb98211cebb9814e93771b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="public-key-infrastructure-for-skype-for-business-server-2015"></a>Infraestrutura de chave pública do Skype for Business Server 2015
 
Skype para Business Server 2015 depende de certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as funções de servidor diferente. O Windows Server 2012 R2, o Windows Server 2012, o Windows Server 2008 R2 e a ferramenta infraestrutura de chave pública (PKI) do Windows Server 2008 fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
  
Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma AC confiável pelos clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar apenas com outros clientes e servidores de rede privada, a AC pode ser uma AC corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.
  
Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.
  
Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado
  
> [!NOTE]
> Nem todas as autoridades de certificação públicas atendem aos requisitos do Skype para certificados Business Server 2015. Recomendamos que consulte a lista de fornecedores certificados de AC pública para suas necessidades de certificados públicos. Para obter detalhes, consulte [Parceiros de certificado do Unified Communications](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Pontos de distribuição das listas de certificados revogados (CRLs)

Skype para Business Server 2015 requer todos os certificados de servidor para conter um ou mais pontos de distribuição da lista de revogação de certificado (CRL). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura.
  
## <a name="enhanced-key-usage"></a>Uso avançado da chave

Skype para Business Server 2015 requer todos os certificados de servidor para dar suporte ao uso avançado de chave (EKU) para fins de autenticação de servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS. É possível ter mais de uma entrada no EKU, permitindo o uso do certificado para mais de uma finalidade.
  

