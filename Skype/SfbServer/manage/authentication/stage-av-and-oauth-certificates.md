---
title: Preparar certificados AV e OAuth Skype for Business Server usando -Roll in Set-CsCertificate
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Resumo: Estágio av e certificados OAuth para Skype for Business Server.'
ms.openlocfilehash: fda09cb53b664419d9652a0b663c83adc770c5cf
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674603"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Preparar certificados AV e OAuth Skype for Business Server usando -Roll in Set-CsCertificate

**Resumo:** Prepare os certificados AV e OAuth para Skype for Business Server.

As comunicações de áudio/vídeo (A/V) são um componente importante do Skype for Business Server. Recursos como compartilhamento de aplicativos e audioconferência de áudio e vídeo dependem dos certificados atribuídos ao serviço A/V Edge, especificamente o serviço de Autenticação A/V.

> [!IMPORTANT]
> Esse novo recurso foi projetado para funcionar para o serviço A/V Edge e o certificado OAuthTokenIssuer. Outros tipos de certificado podem ser provisionados junto com o serviço A/V Edge e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço do A/V Edge beneficiará.

Os cmdlets do PowerShell do Shell de Gerenciamento do Skype for Business Server usados para gerenciar certificados Skype for Business Server referem-se ao certificado de serviço do A/V Edge como o tipo de certificado AudioVideoAuthentication e o certificado OAuthServer como typeOAuthTokenIssuer. Para o restante deste tópico e para identificar exclusivamente os certificados, eles serão referenciados pelo mesmo tipo de identificador, AudioVideoAuthentication eOAuthTokenIssuer.

O serviço de Autenticação A/V é responsável por emitir tokens usados por clientes e outros consumidores A/V. Os tokens são gerados a partir de atributos no certificado e, quando o certificado expirar, a perda de conexão e o requisito de reingressar com um novo token gerado pelo novo certificado resultarão. Um novo recurso no Skype for Business Server aliviará esse problema – a capacidade de preparar um novo certificado antes do antigo expirar e permitir que ambos os certificados continuem a funcionar por um período de tempo. Esse recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate Skype for Business Server Shell de Gerenciamento. O novo parâmetro -Roll, com o parâmetro existente -EffectiveDate, colocará o novo certificado AudioVideoAuthentication no repositório de certificados. O certificado AudioVideoAuthentication mais antigo ainda permanecerá para que os tokens emitidos sejam validados. Começando com a aplicação do novo certificado AudioVideoAuthentication, ocorrerá a seguinte série de eventos:

> [!TIP]
> Usando os cmdlets Skype for Business Server Shell de Gerenciamento para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no Servidor de Borda. Usar o Assistente de Certificado no Assistente de Implantação do Skype for Business Server ajuda você na criação de certificados, mas normalmente é do tipo  padrão que casa todos os certificados que todos os certificados usam para o Servidor de Borda em um único certificado. A prática recomendada se você for usar o recurso de certificado sem interrupção é separar o certificado AudioVideoAuthentication das outras finalidades do certificado. Você pode provisionar e preparar um certificado do tipo Padrão, mas somente a parte AudioVideoAuthentication do certificado combinado se beneficiará do preparo. Um usuário envolvido (por exemplo) em uma conversa de mensagens instantâneas quando o certificado expirar precisará fazer logon e fazer logon novamente para usar o novo certificado associado ao serviço do Access Edge. Um comportamento semelhante ocorrerá para um usuário envolvido em uma webconferência usando o serviço de Borda de WebConferência. O certificado OAuthTokenIssuer é um tipo específico que é compartilhado entre todos os servidores. Você cria e gerencia o certificado em um só lugar e o certificado é armazenado no repositório de Gerenciamento Central para todos os outros servidores.

Detalhes adicionais são necessários para entender totalmente suas opções e requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para preparar certificados antes da expiração do certificado atual. O parâmetro -Roll é importante, mas essencialmente de finalidade única. Se você defini-lo como um parâmetro, você estará informando ao Set-CsCertificate que fornecerá informações sobre o certificado que será afetado definido por -Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornará efetivo definido por -EffectiveDate.

 **-Roll**: o parâmetro -Roll é necessário e tem dependências que devem ser fornecidas junto com ele. Parâmetros necessários para definir totalmente quais certificados serão afetados e como eles serão aplicados:

 **-EffectiveDate**: o parâmetro -EffectiveDate define quando o novo certificado se tornará co-ativo com o certificado atual. O -EffectiveDate pode estar próximo do tempo de expiração do certificado atual ou pode ser um período mais longo. Um -EffectiveDate mínimo recomendado para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida do token padrão para tokens de serviço av Edge emitidos usando o certificado AudioVideoAuthentication.

Ao preparar certificados OAuthTokenIssuer, há requisitos diferentes para o tempo de entrega antes que o certificado possa ser efetivado. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para seu prazo de entrega é de 24 horas antes do tempo de expiração do certificado atual. O tempo de entrega estendido para a coexistência é devido a outras funções de servidor que dependem do certificado OAuthTokenIssuer (Exchange Server, por exemplo), que tem um tempo de retenção mais longo para materiais de chave de criptografia e autenticação criados pelo certificado.

 **-Impressão digital**: a impressão digital é um atributo no certificado que é exclusivo desse certificado. O parâmetro -Thumbprint é usado para identificar o certificado que será afetado pelas ações do Set-CsCertificate cmdlet.

 **-Type**: o parâmetro -Type pode aceitar um único tipo de uso de certificado ou uma lista separada por vírgulas de tipos de uso de certificado. Os tipos de certificado são aqueles que identificam para o cmdlet e para o servidor qual é a finalidade do certificado. Por exemplo, o tipo AudioVideoAuthentication é para uso pelo serviço A/V Edge e pelo serviço de Autenticação av. Se você decidir preparar e provisionar certificados de um tipo diferente ao mesmo tempo, deverá considerar o tempo de entrega mínimo mínimo necessário para os certificados. Por exemplo, você precisa preparar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. Seu -EffectiveDate mínimo deve ser o maior dos dois certificados, nesse caso, o OAuthTokenIssuer, que tem um tempo de entrega mínimo de 24 horas. Se você não quiser preparar o certificado AudioVideoAuthentication com um tempo de entrega de 24 horas, prepare-o separadamente com uma EffectiveDate que seja mais para seus requisitos.

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço do A/V Edge com os parâmetros -Roll e -EffectiveDate

1. Faça logon no computador local como membro do grupo Administradores.

2. Solicite uma renovação ou um novo certificado AudioVideoAuthentication com chave privada exportável para o certificado existente no serviço A/V Edge.

3. Importe o novo certificado AudioVideoAuthentication para o Servidor de Borda e todos os outros Servidores de Borda em seu pool (se você tiver um pool implantado).

4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como a hora de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos o tempo de vida do token (por padrão, oito horas). Isso nos dá uma hora em que o certificado deve ser definido como ativo e é -EffectiveDate \<string\>: "22/7/2015 6:00:00 AM".

   > [!IMPORTANT]
   > Para um pool de Borda, você deve ter todos os certificados AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro -EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções de comunicações A/V devido à expiração do certificado mais antigo antes de todos os tokens de cliente e consumidor serem renovados usando o novo certificado.

   O Set-CsCertificate comando com os parâmetros -Roll e -EffectiveTime:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
   ```

   Um exemplo Set-CsCertificate comando:

   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015 6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate deve ser formatado para corresponder às configurações de região e idioma do servidor. O exemplo usa as configurações região e idioma do inglês dos EUA

Para entender ainda mais o processo que Set-CsCertificate, -Roll e -EffectiveDate usam para preparar um novo certificado para emitir novos tokens AudioVideoAuthentication enquanto ainda usa um certificado existente para validar AudioVideoAuthentication que estão em uso pelos consumidores, uma linha do tempo visual é um meio eficaz de entender o processo. No exemplo a seguir, o administrador determina que o certificado de serviço do A/V Edge deve expirar às 14h em 22/07/2015. Ele solicita e recebe um novo certificado e o importa para cada Servidor de Borda em seu pool. Às 2h de 22/07/2015, ele começa a executar o Get-CsCertificate com -Roll, -Thumbprint igual à cadeia de caracteres de impressão digital do novo certificado e -EffectiveTime definido como 22/07/2015 6:00:00 AM. Ele executa este comando em cada Servidor de Borda.

![Usando os parâmetros Roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)

|Texto explicativo|Etapa|
|:-----|:-----|
|1|Início: 22/07/2015 12:00:00  <br/> O certificado AudioVideoAuthentication atual deve expirar às 14h em 22/07/2015. Isso é determinado pelo carimbo de data/hora expira no certificado. Planeje a substituição e a substituição do certificado para que ele seja contabilizado por uma sobreposição de 8 horas (tempo de vida do token padrão) antes que o certificado existente atinja o tempo de expiração. O tempo de entrega das 2:00:00 é usado neste exemplo para permitir que o administrador coloque e provisione os novos certificados antes da hora efetiva das 6h.|
|2|22/07/2015 2:00:00 – 22/07/2015 5:59:59 AM  <br/> Definir certificados em servidores de borda com a hora efetiva de 6:00:00 (o tempo de entrega de 4 horas é para este exemplo, mas pode ser mais longo) usando Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>|
|3|22/07/2015 6:00 - 22/07/2015 14:00  <br/> Para validar tokens, o novo certificado é tentado primeiro e, se o novo certificado não validar o token, o certificado antigo é tentado. Esse processo é usado para todos os tokens durante o período de sobreposição de 8 horas (tempo de vida do token padrão).|
|4|Fim: 22/07/2015 14:00:01  <br/> O certificado antigo expirou e o novo certificado foi assumido. O certificado antigo pode ser removido com segurança com Remove-CsCertificate -Type \<certificate usage type\> -Previous|

Quando a hora efetiva é atingida (22/07/2015 6:00:00), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de tentar o novo e voltar para o certificado antigo continuará até a hora de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado OAuthTokenIssuer com parâmetros -Roll e -EffectiveDate

1. Faça logon no computador local como membro do grupo Administradores.

2. Solicite uma renovação ou um novo certificado OAuthTokenIssuer com chave privada exportável para o certificado existente no Servidor Front-End.

3. Importe o novo certificado OAuthTokenIssuer para um Servidor Front-End em seu pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e só precisa ser atualizado e renovado em qualquer servidor em sua implantação. O Servidor Front-End é usado como exemplo.

4. Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro -Roll com o parâmetro -EffectiveDate. A data efetiva deve ser definida como a hora de expiração do certificado atual (14:00:00 ou 14:00 PM) menos um mínimo de 24 horas.

    O Set-CsCertificate comando com os parâmetros -Roll e -EffectiveTime:

   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumbprint of new certificate> -Roll -EffectiveDate <date and time for certificate to become active> -identity Global
   ```

Um exemplo Set-CsCertificate comando:

  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015 1:00:00 PM"
  ```

> [!IMPORTANT]
> EffectiveDate deve ser formatado para corresponder às configurações de região e idioma do servidor. O exemplo usa as configurações região e idioma do inglês dos EUA

Quando a hora efetiva é atingida (21/07/2015 1:00:00), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de tentar o novo e voltar para o certificado antigo continuará até a hora de expiração do certificado antigo. Depois que o certificado antigo expirar (22/07/2015 14:00), os tokens só serão validados pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro -Previous.

```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous
```

## <a name="see-also"></a>Confira também

[Gerenciar a autenticação de servidor para servidor (OAuth) e aplicativos parceiros no Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate)

[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate)
