---
title: Infraestrutura de chave pública para Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: Skype for Business Server se baseia em certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. O Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 Public Key Infrastructure (PKI) fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
ms.openlocfilehash: 733b1bb946147edd184a7b0fecb16ffab2adba51
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627923"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infraestrutura de chave pública para Skype for Business Server
 
Skype for Business Server se baseia em certificados para autenticação de servidor e para estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. O Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2 e Windows Server 2008 Public Key Infrastructure (PKI) fornece a infraestrutura para estabelecer e validar essa cadeia de confiança.
  
Os certificados são IDs digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações sobre um certificado sejam válidas, o certificado deve ser emitido por uma AC confiável por clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar somente com outros clientes e servidores em uma rede privada, a CA poderá ser uma CA empresarial. Se o servidor interagir com entidades fora da rede privada, uma CA pública poderá ser necessária.
  
Mesmo que as informações de um certificado sejam válidas, deve haver alguma forma de verificar se o servidor que está apresentando o certificado é realmente o representado pelo certificado. É aqui que a PKI do Windows entra em ação.
  
Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado retém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar uma parte aleatória das informações e enviá-la ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão poderá ter a certeza de que o servidor retém a chave privada para o certificado e, portanto, é o servidor nomeado no certificado.
  
> [!NOTE]
> Nem todas as CAs públicas estão em conformidade com os requisitos Skype for Business Server certificados. Recomendamos a consulta à lista de fornecedores certificados de CA pública para suas necessidades de certificado público. Para obter detalhes, consulte [Unified Communications Certificate Partners](https://go.microsoft.com/fwlink/p/?LinkId=140898). 
  
## <a name="crl-distribution-points"></a>Pontos de distribuição de CRL

Skype for Business Server exige que todos os certificados de servidor contenham um ou mais pontos de distribuição de CRL (Lista de Revogação de Certificados). CDPs (Pontos de distribuição de CRL) são locais a partir dos quais os CRLs podem ser baixados para verificar se o certifico não foi revogado desde que foi emitido e se ainda está dentro do período de validade. Um ponto de distribuição da lista de certificados revogados é especificado nas propriedades do certificado como uma URL e, geralmente, é um HTTP seguro.
  
## <a name="enhanced-key-usage"></a>Uso avançado de chave

Skype for Business Server requer todos os certificados de servidor para dar suporte ao Uso de Chave Aprimorada (EKU) para fins de autenticação de servidor. A configuração do campo de EKU para autenticação de servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para o MTLS. É possível ter mais de uma entrada no EKU, o que habilitará o certificado a mais de uma finalidade.
  

