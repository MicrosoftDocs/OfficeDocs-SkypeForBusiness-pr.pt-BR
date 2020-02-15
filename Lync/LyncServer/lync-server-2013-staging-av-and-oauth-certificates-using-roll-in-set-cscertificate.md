---
title: Preparando o AV e certificados OAuth usando-o-Role no set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Staging AV and OAuth certificates using -Roll in Set-CsCertificate
ms:assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ660292(v=OCS.15)
ms:contentKeyID: 49354387
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a85d39fb80075e4de817c4343040d358ad41eeb5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a>Preparando certificados AV e OAuth no Lync Server 2013 usando-o-rolo no set-CsCertificate

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-13_

A comunicação de áudio/vídeo (A/V) é um componente-chave do Microsoft Lync Server 2013. Recursos como compartilhamento de aplicativos e conferência de áudio e vídeo dependem dos certificados atribuídos ao serviço de borda A/V, especificamente o serviço de autenticação A/V.

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P>Este novo recurso foi projetado para funcionar para o serviço de borda a/V e o certificado <EM>OAuthTokenIssuer</EM> . Outros tipos de certificado podem ser provisionados junto com o serviço de borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de borda A/V usará.</P>
> <LI>
> <P>Os cmdlets do PowerShell do Shell de gerenciamento do Lync Server usados para gerenciar certificados do Microsoft Lync Server 2013 referem-se ao certificado de serviço de borda A/V, como o tipo de certificado <EM>AudioVideoAuthentication</EM> e o certificado OAuthServer como tipo <EM>OAuthTokenIssuer</EM>. Para o restante deste tópico e identificar exclusivamente os certificados, eles serão referidos pelo mesmo tipo de identificador, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</P></LI></OL>



</div>

O serviço de autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores de A/V. Os tokens são gerados a partir de atributos no certificado e quando o certificado expira, a perda de conexão e o requisito de reingresso com um novo token gerado pelo novo certificado resultará. Um novo recurso no Lync Server 2013 amenizará esse problema, a capacidade de preparar um novo certificado com antecedência do antigo expirado e permitir que os dois certificados continuem a funcionar por um período de tempo. Este recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate Lync Server Management Shell. O novo parâmetro – rolo, com o parâmetro existente – EffectiveDate, colocará o novo certificado AudioVideoAuthentication no repositório de certificados. O certificado AudioVideoAuthentication mais antigo ainda permanecerá para que os tokens emitidos sejam validados. Começando com a colocação do novo certificado AudioVideoAuthentication no local, ocorrerão as seguintes séries de eventos:

<div>


> [!TIP]
> Usando os cmdlets do Shell de gerenciamento do Lync Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no servidor de borda. O uso do assistente de certificado no assistente de implantação do Lync Server ajuda na criação de certificados, mas geralmente é o tipo <STRONG>padrão</STRONG> que associa todos os usos de certificado para o servidor de borda em um único certificado. A prática recomendada se você for usar o recurso de certificado sem interrupção é desacoplar o certificado AudioVideoAuthentication das outras finalidades do certificado. Você pode provisionar e testar um certificado do tipo padrão, mas somente a parte AudioVideoAuthentication do certificado combinado se beneficiará da preparação. Um usuário envolvido (por exemplo) uma conversa de mensagem instantânea quando o certificado expirar precisará fazer logout e logon novamente para usar o novo certificado associado ao serviço de borda de acesso. Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência Web usando o serviço de borda de Webconferência. O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores. Você cria e gerencia o certificado em um local e o certificado é armazenado no repositório de gerenciamento central para todos os outros servidores.



</div>

Detalhes adicionais são necessários para entender totalmente as opções e os requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para testar certificados antes do vencimento do certificado atual. O parâmetro – rolo é importante, mas essencialmente um único objetivo. Se você defini-lo como um parâmetro, você está dizendo Set-CsCertificate que você fornecerá informações sobre o certificado que será afetado definido por – Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornar eficaz definido por – EffectiveDate.

**-Rolo:** O parâmetro – rolo é necessário e tem dependências que devem ser fornecidas junto com ele. Parâmetros necessários para definir totalmente quais certificados serão afetados e como eles serão aplicados:

**-EffectiveDate:** O parâmetro – EffectiveDate define quando o novo certificado ficará coativo com o certificado atual. O – EffectiveDate pode ser próximo do tempo de expiração do certificado atual ou pode ser um período de tempo mais longo. Um mínimo recomendado – EffectiveDate para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida de token padrão para tokens de serviço de borda de AV emitidos usando o certificado AudioVideoAuthentication.

Ao preparar certificados do OAuthTokenIssuer, existem diferentes requisitos para o prazo de entrega antes que o certificado possa se tornar efetivo. O tempo mínimo que o certificado OAuthTokenIssuer deve ter para o tempo de avanço é de 24 horas antes do tempo de expiração do certificado atual. O tempo de avanço estendido para a coexistência é devido a outras funções de servidor que são dependentes do certificado OAuthTokenIssuer (Exchange Server, por exemplo) que tem um tempo de retenção mais longo para a autenticação e chave de criptografia criadas pelo certificado necessários.

**– Impressão digital:** A impressão digital é um atributo no certificado que é exclusivo desse certificado. O parâmetro – Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.

**-Type:** O parâmetro – Type pode aceitar um único tipo de uso de certificado ou uma lista separada por vírgulas de tipos de uso de certificado. Os tipos de certificado são aqueles que identificam o cmdlet e para o servidor qual é a finalidade do certificado. Por exemplo, digite AudioVideoAuthentication é para uso pelo serviço de borda A/V e pelo serviço de autenticação AV. Se você decidir preparar e provisionar certificados de um tipo diferente ao mesmo tempo, deverá considerar o tempo de avanço efetivo mínimo necessário para os certificados. Por exemplo, você precisa testar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer. O mínimo – EffectiveDate deve ser o maior dos dois certificados, neste caso, o OAuthTokenIssuer, que tem um tempo de avanço mínimo de 24 horas. Se você não quiser testar o certificado AudioVideoAuthentication com um tempo de avanço de 24 horas, transfira-o separadamente com um EffectiveDate que tenha mais de seus requisitos.

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado de serviço de borda A/V com parâmetros – rolo e-EffectiveDate

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Solicite uma renovação ou um novo certificado AudioVideoAuthentication com a chave privada exportável para o certificado existente no serviço de borda A/V.

3.  Importe o novo certificado AudioVideoAuthentication para o servidor de borda e todos os outros servidores de borda em seu pool (se você tiver um pool implantado).

4.  Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro – rolo com o parâmetro – EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos tempo de vida do token (por padrão, oito horas). Isso nos dá uma hora em que o certificado deve ser definido como ativo e é a cadeia de \<caracteres\>– EFFECTIVEDATE: "7/22/2012 6:00:00 AM".
    
    <div>
    

    > [!IMPORTANT]
    > Para um pool de borda, você deve ter todos os certificados do AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro – EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções de comunicações A/V devido à expiração do certificado mais antigo antes que todos os tokens de cliente e consumidor tenham sido renovados usando o novo certificado.

    
    </div>
    
    O comando Set-CsCertificate com o parâmetro – rolo e – effectiveTime:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Um comando Set-CsCertificate de exemplo:
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de idioma e região inglês dos EUA

    
    </div>

Para entender melhor o processo que o set-CsCertificate,-rolo e – EffectiveDate usa para testar um novo certificado para emitir novos tokens de AudioVideoAuthentication e ainda usar um certificado existente para validar o AudioVideoAuthentication que estão em uso por consumidores, uma linha do tempo Visual é uma maneira eficaz de compreender o processo.

No exemplo a seguir, o administrador determina que o certificado de serviço de borda A/V está prestes a expirar às 2:00:00 PM no 07/22/2012. Ele solicita e recebe um novo certificado e o importa para cada servidor de borda em seu pool. Às 2 AM no 07/22/2012, ele começa a executar Get-CsCertificate com – rolo,-Thumbprint igual à cadeia de caracteres de impressão digital do novo certificado e – Efetivotime definido como 07/22/2012 6:00:00 AM. Ele executa este comando em cada servidor de borda.

![Usando os parâmetros rolo e EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usando os parâmetros rolo e EffectiveDate.")

Quando a hora efetiva é atingida (7/22/2012 6:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de experimentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo expirar (7/22/2012 2:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro – Previous.

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a>Para atualizar ou renovar um certificado OAuthTokenIssuer com parâmetros – rolo e-EffectiveDate

1.  Faça logon no computador local como membro do grupo Administradores.

2.  Solicite uma renovação ou um novo certificado OAuthTokenIssuer com a chave privada exportável para o certificado existente no serviço de borda A/V.

3.  Importe o novo certificado OAuthTokenIssuer para um servidor front-end em seu pool (se você tiver um pool implantado). O certificado OAuthTokenIssuer é replicado globalmente e só precisa ser atualizado e renovado em qualquer servidor em sua implantação. O servidor front-end é usado como um exemplo.

4.  Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro – rolo com o parâmetro – EffectiveDate. A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos de 24 horas.
    
    O comando Set-CsCertificate com o parâmetro – rolo e – effectiveTime:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    Um comando Set-CsCertificate de exemplo:
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor. O exemplo usa as configurações de idioma e região inglês dos EUA

    
    </div>

Quando a hora efetiva é atingida (7/21/2012 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado. Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado. Se a validação falhar, o certificado antigo será tentado. O processo de experimentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo. Quando o certificado antigo expirar (7/22/2012 2:00:00 PM), os tokens serão validados apenas pelo novo certificado. O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro – Previous.

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejar certificados de servidor de borda no Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)  
[Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[Configurar certificados de borda para o Lync Server 2013](lync-server-2013-set-up-edge-certificates.md)  
[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))  
[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

