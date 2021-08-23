---
title: Segurança do aplicativo móvel do Skype for Business
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: d2be8c74-3ba2-4b2d-9807-634904e1f0e8
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Aprenda a configurar a segurança do aplicativo móvel para seus usuários. '
ms.openlocfilehash: 1669204e31c7597ec75f6c30570107bebf440e3b
ms.sourcegitcommit: 9fcd9a7ae78e04cef90415c2a0f30a98fbf8270f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/19/2021
ms.locfileid: "58406980"
---
# <a name="skype-for-business-mobile-app-security"></a>Segurança do aplicativo móvel do Skype for Business

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

## <a name="skype-for-business-client-security"></a>Segurança do Cliente Skype for Business

Este artigo abrange as informações de criptografia de dados em Aplicativos Móveis do Skype for Business.
  
||**Nome de usuário/Senha** <br/> |**Dados do aplicativo (Conversas, <br/> Lista de Contatos, Reuniões)** <br/> |**Logs de diagnóstico** <br/> |
|:-----|:-----|:-----|:-----|
|**Android** <br/> |Armazenamos informações sobre credenciais nas contas do Android. Também criptografamos credenciais antes de salvá-las em Contas. Usamos o algoritmo " **AES/CBC/PKCS5Padding** " para criptografia.<br/> |Armazenamos em um banco de dados SQL criptografado usando uma biblioteca chamada [sqlcipher](https://www.zetetic.net/sqlcipher/design/). Usamos seu algoritmo padrão de AES de 256 bits no modo CBC. Os dados em armazenamento são sempre criptografados no arquivo do banco de dados e são descriptografados somente em trânsito dentro da memória volátil do app e pilhas de chamada. Também criptografamos os arquivos de caixa postal usando o mesmo método que o da criptografia de nome de usuário e senha (eles não são armazenados no banco de dados). As caixas postais são descriptografadas no disco para permitir reprodução.<br/> |Essas informações não são criptografadas.  <br/> |
|**iOS** <br/> |NÃO criptografamos o nome de usuário/senha na cadeia de conjunto de chaves. No entanto, o conjunto de chaves é criptografado sozinho.  <br/> |Já estamos usando a sinalização de proteção de dados [NSFileProtectionCompleteUntilFirstUserAuthentication](https://developer.apple.com/reference/foundation/fileprotectiontype/1616633-completeuntilfirstuserauthentica) em todos os arquivos no armazenamento do aplicativo. Isso significa que os arquivos no armazenamento do aplicativo seriam criptografados até o usuário desbloquear o dispositivo pela primeira vez após sua reinicialização.<br/> |Essas informações não são criptografadas.  <br/> |
|**Windows Phone** <br/> |O Windows Phone usa o DPAPI (Data Protection API) no Windows para proteger senhas. Acredito que o esquema de criptografia usado é o AES. O Windows não fornece uma opção para configurar o tamanho da chave (ou esquema), portanto, a chave terá o tamanho dado pelo DPAPI. Ele usará o TPM do dispositivo para proteger as chaves que são específicas para o usuário e o dispositivo. Note que as chaves DPAPI não são específicas para o aplicativo.  <br/> |Os dados do aplicativo WP são protegidos com o [DPAP](/previous-versions/windows/apps/hh487164(v=vs.105))I, como as credenciais. Dependendo de quantos detalhes desejamos, algumas informações do índice para os Dados do App são protegidas por criptografia AES (não DPAPI) para evitar salting, assim, podemos conferir sem descriptografa. Por sua vez , essa chave é protegida com DPAPI. Os dados em cache podem ser lidos por qualquer processo por meio do mesmo telefone, presumindo que ele possa acessar nossa pasta de dados. A criptografia do Windows não protege contra a violação da área restrita, apenas contra tentativas de acesso externo.<br/> |Essas informações não são criptografadas.  <br/> |
   
**Observação:** Consulte esta [documentação pública para imposição](/InTune/deploy-use/introduction-to-device-compliance-policies-in-microsoft-intune) de pino de dispositivo disponível em cada uma das plataformas Móveis acima
  
## <a name="related-topics"></a>Tópicos relacionados
[Instalar o Skype for Business Online](set-up-skype-for-business-online.md)

[Permitir que os usuários do Skype for Business adicionem contatos do Skype](let-skype-for-business-users-add-skype-contacts.md)

  
