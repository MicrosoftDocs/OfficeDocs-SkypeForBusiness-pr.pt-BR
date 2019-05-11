---
title: Atribuir um certificado de autenticação de servidor-para-servidor ao Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c7413954-2504-47f4-a073-44548aff1c0c
description: 'Resumo: Atribua um certificado de autenticação de servidor-para-servidor para Skype para Business Server.'
ms.openlocfilehash: 761234f821f5d95d53f7188a7197b28710d23893
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902752"
---
# <a name="assign-a-server-to-server-authentication-certificate-to-skype-for-business-server"></a>Atribuir um certificado de autenticação de servidor-para-servidor ao Skype para Business Server
**Resumo:** Atribua um certificado de autenticação de servidor-para-servidor para Skype para Business Server.
  
Para determinar se ou não um certificado de autenticação de servidor-para-servidor já tenha sido atribuído a Skype para Business Server, execute o seguinte comando do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Get-CsCertificate -Type OAuthTokenIssuer
```

Se nenhuma informação de certificado for retornada, você deverá atribuir um certificado emissor de token antes de poder usar a autenticação servidor- servidor. Como regra geral, qualquer Skype para o certificado de servidor de negócios pode ser usado como seu certificado OAuthTokenIssuer; Por exemplo, seu Skype para o certificado do servidor de negócios padrão também pode ser usado como o certificado OAuthTokenIssuer. (O certificado OAUthTokenIssuer também pode ser qualquer certificado de servidor Web que inclui o nome do seu domínio SIP no campo assunto.) Os dois requisitos principais para o certificado usado para autenticação de servidor-para-servidor são estes: 1) o mesmo certificado deve ser configurado como o certificado OAuthTokenIssuer em todos os seus servidores Front-End; e, 2) o certificado deve ser de pelo menos 2048 bits.
  
Se você não tiverum certificado que possa ser usado para autenticação servidor-servidor, é possível obter um novo certificado, importá-lo e usar para autenticação servidor-servidor. Após ter obtido o novo certificado e solicitado pode fazer logon em qualquer um dos seus servidores Front-End e usar um comando do Windows PowerShell semelhante a essa para importar e atribuir o certificado:
  
```
Import-CsCertificate -Identity global -Type OAuthTokenIssuer -Path C:\Certificates\ServerToServerAuth.pfx  -Password "P@ssw0rd"
```

No comando anterior, o parâmetro Path representa o caminho completo para o arquivo de certificado e o parâmetro Password representa a senha atribuída ao certificado. Esse procedimento deve ser executado apenas uma vez: o Skype para o serviço de replicação do servidor de negócios, em seguida, criará automaticamente um conjunto de tarefas agendadas que hospedará descriptografar e implantar o certificado em todos os seus servidores Front-End.
  
Como alternativa, é possível usar um certificado existente como seu certificado de autenticação servidor-servidor. (Conforme observado, o certificado padrão pode ser usado como o certificado de autenticação de servidor-para-servidor.) O seguinte par de comandos do Windows PowerShell recupera o valor da propriedade de impressão digital do certificado padrão, depois de usar esse valor para fazer com que o padrão o certificado de autenticação de servidor-para-servidor de certificado:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x
```

No comando anterior, o certificado recuperado é configurado para funcionar como o certificado de autenticação de servidor-para-servidor global; Isso significa que o certificado será replicado e usado por, todos os seus servidores Front-End. Novamente, este comando deve ser executado somente uma vez e apenas em um dos seus servidores Front-End. Embora todos os servidores Front-End deve usar o mesmo certificado, você não deve configurar o certificado OAuthTokenIssuer em cada servidor Front-End. Em vez disso, configure o certificado de uma vez e permitir que o Skype para o servidor de duplicação Business Server cuidam de copiar o certificado para cada servidor.
  
O cmdlet Set-CsCertificate leva o certificado em questão e configura o certificado para agir como o certificado OAuthTokenIssuer atual imediatamente. (Skype para Business Server mantém duas cópias de um tipo de certificado: o certificado atual e o certificado anterior.) Se você precisar o novo certificado para iniciar imediatamente agir como o certificado OAuthTokenIssuer, em seguida, você deve usar o cmdlet Set-CsCertificate.
  
Também é possível usar o cmdlet Set-CsCertificate para "criar" um novo certificado. "Criar" um certificado simplesmente significa que você configura um novo certificado para se tornar o certificado OAuthTokenIssuer atual em um determinado ponto no tempo. Por exemplo, esse comando recupera o certificado padrão e configura o certificado para assumir como o certificado OAuthTokenIssuer atual a partir de 1° de julho de 2015:
  
```
$x = (Get-CsCertificate -Type Default).Thumbprint
Set-CsCertificate -Identity global -Type OAuthTokenIssuer -Thumbprint $x -EffectiveDate "7/1/2015" -Roll
```

Em 1º de julho de 2015, o novo certificado será configurado como o certificado OAuthTokenIssuer atual e o certificado OAuthTokenIssuer "antigo" será configurado como o certificado anterior.
  
Se você não quiser usar o Windows PowerShell, você também pode usar o console do MMC de certificados para exportar um certificado de um servidor Front-End e depois importar o mesmo certificado em todos os seus outros servidores Front-End. Se você fizer isso, certifique-se de exportar a chave privada junto com o próprio certificado.
  
> [!CAUTION]
> Nesse caso, o procedimento deve ser executado em cada servidor Front-End. Quando a exportação e importação de certificados dessa maneira Skype para Business Server não replicará esse certificado para cada servidor Front-End. 
  
Depois que o certificado foi importado para todos os seus servidores Front-End, esse certificado pode ser atribuído usando o Skype para o Assistente de implantação Business Server, em vez do Windows PowerShell. Para atribuir um certificado usando o Assistente de Implantação, conclua as seguintes etapas em um computador no qual o Assistente de Implantação tenha sido instalado:
  
1. Clique em Iniciar, clique em todos os programas, clique **Skype para Business Server**e clique em **Skype para o Assistente de implantação de servidor de negócios**.
    
2. No Assistente de implantação, clique em **instalar ou Skype de atualização para o sistema de servidor de negócios**.
    
3. Sobre o Skype para página Business Server, clique no botão **Executar** , sob o título **etapa 3: solicitar, instalar ou atribuir certificados**. (Observação: Se você já tiver instalado certificados neste computador, o botão **Executar** será chamado **Executar novamente**.)
    
4. No Assistente de Certificado, selecione o certificado **OAuthTokenIssuer** e clique em **Atribuir**.
    
5. No assistente de Atribuição de Certificado, na página **Atribuição de certificado**, clique em **Avançar**.
    
6. Na página **Repositório de Certificado**, selecione o certificado a ser usado para autenticação servidor-servidor e clique em **Avançar**.
    
7. Na página Resumo da Atribuição de Certificado, clique em **Avançar**.
    
8. Na página Executando Comandos, clique em **Concluir**.
    
9. Feche o Assistente de Certificado e Assistente de Implantação.
    

