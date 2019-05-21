---
title: Infraestrutura de chave pública para o Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 737c8a25-23e9-4494-ab76-5a7b729b44ca
description: O Skype for Business Server depende de certificados para autenticação de servidor e de estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. A infraestrutura de chave pública (PKI) do Windows Server 2012 R2, Windows Server 2012, do Windows Server 2008 R2 e do Windows Server 2008 fornece a infraestrutura para o estabelecimento e a validação da cadeia de confiança.
ms.openlocfilehash: 381afce84c1a58d15187547c9cb8fd6f98e84790
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296851"
---
# <a name="public-key-infrastructure-for-skype-for-business-server"></a>Infraestrutura de chave pública para o Skype for Business Server
 
O Skype for Business Server depende de certificados para autenticação de servidor e de estabelecer uma cadeia de confiança entre clientes e servidores e entre as diferentes funções de servidor. A infraestrutura de chave pública (PKI) do Windows Server 2012 R2, Windows Server 2012, do Windows Server 2008 R2 e do Windows Server 2008 fornece a infraestrutura para o estabelecimento e a validação da cadeia de confiança.
  
Certificados são identificações digitais. Eles identificam um servidor por nome e especificam suas propriedades. Para garantir que as informações em um certificado sejam válidas, o certificado deve ser emitido por uma AC confiável pelos clientes ou outros servidores que se conectam ao servidor. Se o servidor se conectar apenas com outros clientes e servidores de rede privada, a AC pode ser uma AC corporativa. Se o servidor interagir com entidades fora da rede privada, uma AC pública pode ser necessária.
  
Mesmo se as informações no certificado forem válidas, deve haver uma forma de verificar se o servidor que apresenta o certificado é de fato aquele representado pelo certificado. É nessa etapa que o PKI do Windows entrará.
  
Cada certificado é vinculado a uma chave pública. O servidor nomeado no certificado mantém uma chave privada correspondente que somente ele conhece. Um cliente ou servidor de conexão usa a chave pública para criptografar partes aleatórias das informações e as envia ao servidor. Se o servidor descriptografar as informações e retorná-las como texto sem formatação, a entidade de conexão pode se assegurar de que o servidor vincula a chave privada ao certificado e, portanto, o servidor é nomeado no certificado
  
> [!NOTE]
> Nem todas as CAs públicas estão em conformidade com os requisitos dos certificados do Skype for Business Server. Recomendamos que consulte a lista de fornecedores certificados de AC pública para suas necessidades de certificados públicos. Para obter detalhes, consulte [parceiros de certificado de Comunicação](https://go.microsoft.com/fwlink/p/?LinkId=140898)unificada. 
  
## <a name="crl-distribution-points"></a>Pontos de distribuição das listas de certificados revogados (CRLs)

O Skype for Business Server exige que todos os certificados do servidor contenham um ou mais pontos de distribuição da lista de certificados revogados (CRL). Os pontos de distribuição (CDP) de CRL são locais dos quais as CRLs podem ser baixadas para verificar se o certificado não foi revogado desde sua emissão e se o certificado continua dentro do período de validade. Um ponto de distribuição de CRL pode ser encontrado nas propriedades do certificado como uma URL e é normalmente uma HTTP segura.
  
## <a name="enhanced-key-usage"></a>Uso avançado da chave

O Skype for Business Server exige que todos os certificados do servidor sejam compatíveis com o uso avançado da chave (EKU) para a finalidade da autenticação do servidor. A configuração do campo do EKU para autenticação do servidor significa que o certificado é válido para fins de autenticação de servidores. Esse EKU é essencial para MTLS. É possível ter mais de uma entrada no EKU, permitindo o uso do certificado para mais de uma finalidade.
  

