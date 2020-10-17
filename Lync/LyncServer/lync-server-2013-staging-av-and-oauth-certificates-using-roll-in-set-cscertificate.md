---
title: Preparando o AV e certificados OAuth usando-o Set-CsCertificate
description: Preparação de certificados AV e OAuth usando-o-Role no set-CsCertificate.
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
ms.openlocfilehash: 3732c4adb4327cc1e4111307ab2d72ed080cf221
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541837"
---
# <a name="staging-av-and-oauth-certificates-in-lync-server-2013-using--roll-in-set-cscertificate"></a><span data-ttu-id="8740e-103">Preparando certificados de AV e OAuth no Lync Server 2013 usando-redistribuir Set-CsCertificate</span><span class="sxs-lookup"><span data-stu-id="8740e-103">Staging AV and OAuth certificates in Lync Server 2013 using -Roll in Set-CsCertificate</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8740e-104">_**Última modificação do tópico:** 2012-11-13_</span><span class="sxs-lookup"><span data-stu-id="8740e-104">_**Topic Last Modified:** 2012-11-13_</span></span>

<span data-ttu-id="8740e-105">A comunicação de áudio/vídeo (A/V) é um componente-chave do Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8740e-105">Audio/Video (A/V) communications is a key component of Microsoft Lync Server 2013.</span></span> <span data-ttu-id="8740e-106">Recursos como compartilhamento de aplicativos e conferência de áudio e vídeo dependem dos certificados atribuídos ao serviço de borda A/V, especificamente o serviço de autenticação A/V.</span><span class="sxs-lookup"><span data-stu-id="8740e-106">Features such as application sharing and audio and video conferencing rely on the certificates assigned to the A/V Edge service, specifically the A/V Authentication service.</span></span>

<div>


> [!IMPORTANT]
> <OL>
> <LI>
> <P><span data-ttu-id="8740e-107">Este novo recurso foi projetado para funcionar para o serviço de borda a/V e o certificado <EM>OAuthTokenIssuer</EM> .</span><span class="sxs-lookup"><span data-stu-id="8740e-107">This new feature is designed to work for the A/V Edge service and the <EM>OAuthTokenIssuer</EM> certificate.</span></span> <span data-ttu-id="8740e-108">Outros tipos de certificado podem ser provisionados junto com o serviço de borda A/V e o tipo de certificado OAuth, mas não se beneficiarão do comportamento de coexistência que o certificado de serviço de borda A/V usará.</span><span class="sxs-lookup"><span data-stu-id="8740e-108">Other certificate types can be provisioned along with the A/V Edge service and OAuth certificate type, but will not benefit from the coexistence behavior that the A/V Edge service certificate will.</span></span></P>
> <LI>
> <P><span data-ttu-id="8740e-109">Os cmdlets do PowerShell do Shell de gerenciamento do Lync Server usados para gerenciar certificados do Microsoft Lync Server 2013 referem-se ao certificado de serviço de borda A/V, como o tipo de certificado <EM>AudioVideoAuthentication</EM> e o certificado OAuthServer como tipo <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="8740e-109">The Lync Server Management Shell PowerShell cmdlets used to manage Microsoft Lync Server 2013 certificates refers to the A/V Edge service certificate as the <EM>AudioVideoAuthentication</EM> certificate type and the OAuthServer certificate as type <EM>OAuthTokenIssuer</EM>.</span></span> <span data-ttu-id="8740e-110">Para o restante deste tópico e identificar exclusivamente os certificados, eles serão referidos pelo mesmo tipo de identificador, <EM>AudioVideoAuthentication</EM> e <EM>OAuthTokenIssuer</EM>.</span><span class="sxs-lookup"><span data-stu-id="8740e-110">For the rest of this topic and to uniquely identify the certificates, they will be referred to by the same identifier type, <EM>AudioVideoAuthentication</EM> and <EM>OAuthTokenIssuer</EM>.</span></span></P></LI></OL>



</div>

<span data-ttu-id="8740e-111">O serviço de autenticação A/V é responsável por emitir tokens que são usados por clientes e outros consumidores de A/V.</span><span class="sxs-lookup"><span data-stu-id="8740e-111">The A/V Authentication service is responsible for issuing tokens that are used by clients and other A/V consumers.</span></span> <span data-ttu-id="8740e-112">Os tokens são gerados a partir de atributos no certificado e quando o certificado expira, a perda de conexão e o requisito de reingresso com um novo token gerado pelo novo certificado resultará.</span><span class="sxs-lookup"><span data-stu-id="8740e-112">The tokens are generated from attributes on the certificate, and when the certificate expires, loss of connection and requirement to rejoin with a new token generated by the new certificate will result.</span></span> <span data-ttu-id="8740e-113">Um novo recurso no Lync Server 2013 amenizará esse problema, a capacidade de preparar um novo certificado com antecedência do antigo expirado e permitir que os dois certificados continuem a funcionar por um período de tempo.</span><span class="sxs-lookup"><span data-stu-id="8740e-113">A new feature in Lync Server 2013 will alleviate this problem – the ability to stage a new certificate in advance of the old one expiring and allowing both certificates to continue to function for a period of time.</span></span> <span data-ttu-id="8740e-114">Este recurso usa a funcionalidade atualizada no cmdlet Set-CsCertificate Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="8740e-114">This feature uses updated functionality in the Set-CsCertificate Lync Server Management Shell cmdlet.</span></span> <span data-ttu-id="8740e-115">O novo parâmetro – rolo, com o parâmetro existente – EffectiveDate, colocará o novo certificado AudioVideoAuthentication no repositório de certificados.</span><span class="sxs-lookup"><span data-stu-id="8740e-115">The new parameter –Roll, with the existing parameter –EffectiveDate, will place the new AudioVideoAuthentication certificate in the certificate store.</span></span> <span data-ttu-id="8740e-116">O certificado AudioVideoAuthentication mais antigo ainda permanecerá para que os tokens emitidos sejam validados.</span><span class="sxs-lookup"><span data-stu-id="8740e-116">The older AudioVideoAuthentication certificate will still remain for issued tokens to be validated against.</span></span> <span data-ttu-id="8740e-117">Começando com a colocação do novo certificado AudioVideoAuthentication no local, ocorrerão as seguintes séries de eventos:</span><span class="sxs-lookup"><span data-stu-id="8740e-117">Beginning with putting the new AudioVideoAuthentication certificate in place, the following series of events will occur:</span></span>

<div>


> [!TIP]
> <span data-ttu-id="8740e-118">Usando os cmdlets do Shell de gerenciamento do Lync Server para gerenciar certificados, você pode solicitar certificados separados e distintos para cada finalidade no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8740e-118">Using the Lync Server Management Shell cmdlets for managing certificates, you can request separate and distinct certificates for each purpose on the Edge Server.</span></span> <span data-ttu-id="8740e-119">O uso do assistente de certificado no assistente de implantação do Lync Server ajuda na criação de certificados, mas geralmente é o tipo <STRONG>padrão</STRONG> que associa todos os usos de certificado para o servidor de borda em um único certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-119">Using the Certificate Wizard in the Lync Server Deployment Wizard assists you in creating certificates, but is typically of the <STRONG>default</STRONG> type which couples all certificate uses for the Edge Server onto a single certificate.</span></span> <span data-ttu-id="8740e-120">A prática recomendada se você for usar o recurso de certificado sem interrupção é desacoplar o certificado AudioVideoAuthentication das outras finalidades do certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-120">The recommended practice if you are going to use the rolling certificate feature is to decouple the AudioVideoAuthentication certificate from the other certificate purposes.</span></span> <span data-ttu-id="8740e-121">Você pode provisionar e testar um certificado do tipo padrão, mas somente a parte AudioVideoAuthentication do certificado combinado se beneficiará da preparação.</span><span class="sxs-lookup"><span data-stu-id="8740e-121">You can provision and stage a certificate of the Default type, but only the AudioVideoAuthentication portion of the combined certificate will benefit from the staging.</span></span> <span data-ttu-id="8740e-122">Um usuário envolvido (por exemplo) uma conversa de mensagem instantânea quando o certificado expirar precisará fazer logout e logon novamente para usar o novo certificado associado ao serviço de borda de acesso.</span><span class="sxs-lookup"><span data-stu-id="8740e-122">A user involved in (for example) an instant messaging conversation when the certificate expires will need to log out and log back in to make use of the new certificate associated with the Access Edge service.</span></span> <span data-ttu-id="8740e-123">Comportamento semelhante ocorrerá para um usuário envolvido em uma conferência Web usando o serviço de borda de Webconferência.</span><span class="sxs-lookup"><span data-stu-id="8740e-123">Similar behavior will occur for a user involved in a Web conference using the Web Conferencing Edge service.</span></span> <span data-ttu-id="8740e-124">O certificado OAuthTokenIssuer é um tipo específico compartilhado em todos os servidores.</span><span class="sxs-lookup"><span data-stu-id="8740e-124">The OAuthTokenIssuer certificate is a specific type that is shared across all servers.</span></span> <span data-ttu-id="8740e-125">Você cria e gerencia o certificado em um local e o certificado é armazenado no repositório de gerenciamento central para todos os outros servidores.</span><span class="sxs-lookup"><span data-stu-id="8740e-125">You create and manage the certificate in one place and the certificate is stored in the Central Management store for all other servers.</span></span>



</div>

<span data-ttu-id="8740e-126">É necessário mais detalhes para compreender totalmente as opções e os requisitos ao usar o cmdlet Set-CsCertificate e usá-lo para testar certificados antes do vencimento do certificado atual.</span><span class="sxs-lookup"><span data-stu-id="8740e-126">Additional detail is needed to fully understand your options and requirements when using the Set-CsCertificate cmdlet and using it to stage certificates prior to the current certificate expiring.</span></span> <span data-ttu-id="8740e-127">O parâmetro – rolo é importante, mas essencialmente um único objetivo.</span><span class="sxs-lookup"><span data-stu-id="8740e-127">The –Roll parameter is important, but essentially single purpose.</span></span> <span data-ttu-id="8740e-128">Se você defini-lo como um parâmetro, você está dizendo Set-CsCertificate de que você fornecerá informações sobre o certificado que será afetado definido por – Type (por exemplo, AudioVideoAuthentication e OAuthTokenIssuer), quando o certificado se tornará efetivo definido por – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8740e-128">If you define it as a parameter, you are telling Set-CsCertificate that you will be providing information about the certificate that will be affected defined by –Type (for example AudioVideoAuthentication and OAuthTokenIssuer), when the certificate will become effective defined by –EffectiveDate.</span></span>

<span data-ttu-id="8740e-129">**-Rolo:** O parâmetro – rolo é necessário e tem dependências que devem ser fornecidas junto com ele.</span><span class="sxs-lookup"><span data-stu-id="8740e-129">**-Roll:** The –Roll parameter is required and has dependencies that must be supplied along with it.</span></span> <span data-ttu-id="8740e-130">Parâmetros necessários para definir totalmente quais certificados serão afetados e como eles serão aplicados:</span><span class="sxs-lookup"><span data-stu-id="8740e-130">Required parameters to fully define which certificates will be affected and how they will be applied:</span></span>

<span data-ttu-id="8740e-131">**-EffectiveDate:** O parâmetro – EffectiveDate define quando o novo certificado ficará coativo com o certificado atual.</span><span class="sxs-lookup"><span data-stu-id="8740e-131">**-EffectiveDate:** The parameter –EffectiveDate defines when the new certificate will become co-active with the current certificate.</span></span> <span data-ttu-id="8740e-132">O – EffectiveDate pode ser próximo do tempo de expiração do certificado atual ou pode ser um período de tempo mais longo.</span><span class="sxs-lookup"><span data-stu-id="8740e-132">The –EffectiveDate can be close to the expiry time of the current certificate, or it can be a longer period of time.</span></span> <span data-ttu-id="8740e-133">Um mínimo recomendado – EffectiveDate para o certificado AudioVideoAuthentication seria de 8 horas, que é o tempo de vida de token padrão para tokens de serviço de borda de AV emitidos usando o certificado AudioVideoAuthentication.</span><span class="sxs-lookup"><span data-stu-id="8740e-133">A recommended minimum –EffectiveDate for the AudioVideoAuthentication certificate would be 8 hours, which is the default token lifetime for AV Edge service tokens issued using the AudioVideoAuthentication certificate.</span></span>

<span data-ttu-id="8740e-134">Ao preparar certificados do OAuthTokenIssuer, existem diferentes requisitos para o prazo de entrega antes que o certificado possa se tornar efetivo.</span><span class="sxs-lookup"><span data-stu-id="8740e-134">When staging OAuthTokenIssuer certificates, there are different requirements for the lead time before the certificate can become effective.</span></span> <span data-ttu-id="8740e-135">O tempo mínimo que o certificado OAuthTokenIssuer deve ter para o tempo de avanço é de 24 horas antes do tempo de expiração do certificado atual.</span><span class="sxs-lookup"><span data-stu-id="8740e-135">The minimum time that the OAuthTokenIssuer certificate should have for its lead time is 24 hours before the expiration time of the current certificate.</span></span> <span data-ttu-id="8740e-136">O tempo de avanço estendido para a coexistência é devido a outras funções de servidor que são dependentes do certificado OAuthTokenIssuer (servidor Exchange, por exemplo), que tem um tempo de retenção mais longo para a autenticação de certificado criada e materiais de chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="8740e-136">The extended lead time for the coexistence is because of other server roles that are dependent on the OAuthTokenIssuer certificate (Exchange Server, for example) which has a longer retention time for certificate created authentication and encryption key materials.</span></span>

<span data-ttu-id="8740e-137">**– Impressão digital:** A impressão digital é um atributo no certificado que é exclusivo desse certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-137">**-Thumbprint:** The thumbprint is an attribute on the certificate that is unique to that certificate.</span></span> <span data-ttu-id="8740e-138">O parâmetro – Thumbprint é usado para identificar o certificado que será afetado pelas ações do cmdlet Set-CsCertificate.</span><span class="sxs-lookup"><span data-stu-id="8740e-138">The –Thumbprint parameter is used to identify the certificate that will be affected by the actions of the Set-CsCertificate cmdlet.</span></span>

<span data-ttu-id="8740e-139">**-Type:** O parâmetro – Type pode aceitar um único tipo de uso de certificado ou uma lista separada por vírgulas de tipos de uso de certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-139">**-Type:** The –Type parameter can accept a single certificate usage type or a comma separated list of certificate usage types.</span></span> <span data-ttu-id="8740e-140">Os tipos de certificado são aqueles que identificam o cmdlet e para o servidor qual é a finalidade do certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-140">The certificate types are those that identify to the cmdlet and to the server what the purpose of the certificate is.</span></span> <span data-ttu-id="8740e-141">Por exemplo, digite AudioVideoAuthentication é para uso pelo serviço de borda A/V e pelo serviço de autenticação AV.</span><span class="sxs-lookup"><span data-stu-id="8740e-141">For example, type AudioVideoAuthentication is for use by the A/V Edge service and the AV Authentication service.</span></span> <span data-ttu-id="8740e-142">Se você decidir preparar e provisionar certificados de um tipo diferente ao mesmo tempo, deverá considerar o tempo de avanço efetivo mínimo necessário para os certificados.</span><span class="sxs-lookup"><span data-stu-id="8740e-142">If you decide to stage and provision certificates of a different type at the same time, you must consider the longest required minimum effective lead time for the certificates.</span></span> <span data-ttu-id="8740e-143">Por exemplo, você precisa testar certificados do tipo AudioVideoAuthentication e OAuthTokenIssuer.</span><span class="sxs-lookup"><span data-stu-id="8740e-143">For example, you need to stage certificates of type AudioVideoAuthentication and OAuthTokenIssuer.</span></span> <span data-ttu-id="8740e-144">O mínimo – EffectiveDate deve ser o maior dos dois certificados, neste caso, o OAuthTokenIssuer, que tem um tempo de avanço mínimo de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8740e-144">Your minimum –EffectiveDate must be the greater of the two certificates, in this case the OAuthTokenIssuer, which has a minimum lead time of 24 hours.</span></span> <span data-ttu-id="8740e-145">Se você não quiser testar o certificado AudioVideoAuthentication com um tempo de avanço de 24 horas, transfira-o separadamente com um EffectiveDate que tenha mais de seus requisitos.</span><span class="sxs-lookup"><span data-stu-id="8740e-145">If you do not want to stage the AudioVideoAuthentication certificate with a lead time of 24 hours, stage it separately with an EffectiveDate that is more to your requirements.</span></span>

<div>

## <a name="to-update-or-renew-an-av-edge-service-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="8740e-146">Para atualizar ou renovar um certificado de serviço de borda A/V com parâmetros – rolo e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="8740e-146">To update or renew an A/V Edge service certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="8740e-147">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="8740e-147">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8740e-148">Solicite uma renovação ou um novo certificado AudioVideoAuthentication com a chave privada exportável para o certificado existente no serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="8740e-148">Request a renewal or new AudioVideoAuthentication certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="8740e-149">Importe o novo certificado AudioVideoAuthentication para o servidor de borda e todos os outros servidores de borda em seu pool (se você tiver um pool implantado).</span><span class="sxs-lookup"><span data-stu-id="8740e-149">Import the new AudioVideoAuthentication certificate to the Edge Server and all other Edge Server in your pool (if you have a pool deployed).</span></span>

4.  <span data-ttu-id="8740e-150">Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro – rolo com o parâmetro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8740e-150">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="8740e-151">A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos tempo de vida do token (por padrão, oito horas).</span><span class="sxs-lookup"><span data-stu-id="8740e-151">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus token lifetime (by default eight hours).</span></span> <span data-ttu-id="8740e-152">Isso nos dá um tempo em que o certificado deve ser definido como ativo e é o – EffectiveDate \<string\> : "7/22/2012 6:00:00 AM".</span><span class="sxs-lookup"><span data-stu-id="8740e-152">This gives us a time that the certificate must be set to active, and is the –EffectiveDate \<string\>: “7/22/2012 6:00:00 AM”.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8740e-153">Para um pool de borda, você deve ter todos os certificados do AudioVideoAuthentication implantados e provisionados pela data e hora definidas pelo parâmetro – EffectiveDate do primeiro certificado implantado para evitar possíveis interrupções de comunicações A/V devido à expiração do certificado mais antigo antes que todos os tokens de cliente e consumidor tenham sido renovados usando o novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-153">For an Edge pool, you must have all AudioVideoAuthentication certificates deployed and provisioned by the date and time defined by the –EffectiveDate parameter of the first certificate deployed to avoid possible A/V communications disruption due to the older certificate expiring before all client and consumer tokens have been renewed using the new certificate.</span></span>

    
    </div>
    
    <span data-ttu-id="8740e-154">O comando Set-CsCertificate com o parâmetro – rolo e – effectiveTime:</span><span class="sxs-lookup"><span data-stu-id="8740e-154">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="8740e-155">Um exemplo Set-CsCertificate comando:</span><span class="sxs-lookup"><span data-stu-id="8740e-155">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2012 6:00:00 AM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8740e-156">O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="8740e-156">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="8740e-157">O exemplo usa as configurações de idioma e região inglês dos EUA</span><span class="sxs-lookup"><span data-stu-id="8740e-157">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="8740e-158">Para entender melhor o processo que o set-CsCertificate,-rolo e – EffectiveDate usa para testar um novo certificado para emitir novos tokens de AudioVideoAuthentication e, ao mesmo tempo, usar um certificado existente para validar o AudioVideoAuthentication que estão sendo usados por consumidores, uma linha do tempo Visual é uma maneira eficaz de compreender o processo.</span><span class="sxs-lookup"><span data-stu-id="8740e-158">To further understand the process that Set-CsCertificate, -Roll, and –EffectiveDate use to stage a new certificate for issuing new AudioVideoAuthentication tokens while still using an existing certificate to validate AudioVideoAuthentication that are in use by consumers, a visual timeline is an effective means of understanding the process.</span></span>

<span data-ttu-id="8740e-159">No exemplo a seguir, o administrador determina que o certificado de serviço de borda A/V está prestes a expirar às 2:00:00 PM no 07/22/2012.</span><span class="sxs-lookup"><span data-stu-id="8740e-159">In the following example, the administrator determines that the A/V Edge service certificate is due to expire at 2:00:00 PM on 07/22/2012.</span></span> <span data-ttu-id="8740e-160">Ele solicita e recebe um novo certificado e o importa para cada servidor de borda em seu pool.</span><span class="sxs-lookup"><span data-stu-id="8740e-160">He requests and receives a new certificate and imports it to each Edge Server in his pool.</span></span> <span data-ttu-id="8740e-161">Às 2 AM no 07/22/2012, ele começa a executar Get-CsCertificate com – rolo,-Thumbprint igual à cadeia de caracteres de impressão digital do novo certificado e – effectiveTime definido como 07/22/2012 6:00:00 AM.</span><span class="sxs-lookup"><span data-stu-id="8740e-161">At 2 AM on 07/22/2012, he begins running Get-CsCertificate with –Roll, -Thumbprint equal to the thumbprint string of the new certificate, and –EffectiveTime set to 07/22/2012 6:00:00 AM.</span></span> <span data-ttu-id="8740e-162">Ele executa este comando em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="8740e-162">He runs this command on each Edge Server.</span></span>

<span data-ttu-id="8740e-163">![Usando os parâmetros rolo e EffectiveDate.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Usando os parâmetros rolo e EffectiveDate.")</span><span class="sxs-lookup"><span data-stu-id="8740e-163">![Using the Roll and the EffectiveDate parameters.](images/JJ660292.21d51a76-0d03-4ed7-a37e-a7c14940265f(OCS.15).jpg "Using the Roll and the EffectiveDate parameters.")</span></span>

<span data-ttu-id="8740e-164">Quando a hora efetiva é atingida (7/22/2012 6:00:00 AM), todos os novos tokens são emitidos pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-164">When the effective time is reached (7/22/2012 6:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="8740e-165">Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-165">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="8740e-166">Se a validação falhar, o certificado antigo será tentado.</span><span class="sxs-lookup"><span data-stu-id="8740e-166">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="8740e-167">O processo de experimentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo.</span><span class="sxs-lookup"><span data-stu-id="8740e-167">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="8740e-168">Quando o certificado antigo expirar (7/22/2012 2:00:00 PM), os tokens serão validados apenas pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-168">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="8740e-169">O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro – Previous.</span><span class="sxs-lookup"><span data-stu-id="8740e-169">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type AudioVideoAuthentication -Previous

</div>

<div>

## <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a-roll-and--effectivedate-parameters"></a><span data-ttu-id="8740e-170">Para atualizar ou renovar um certificado OAuthTokenIssuer com parâmetros – rolo e-EffectiveDate</span><span class="sxs-lookup"><span data-stu-id="8740e-170">To update or renew an OAuthTokenIssuer certificate with a –Roll and -EffectiveDate parameters</span></span>

1.  <span data-ttu-id="8740e-171">Faça logon no computador local como membro do grupo Administradores.</span><span class="sxs-lookup"><span data-stu-id="8740e-171">Log on to the local computer as a member of the Administrators group.</span></span>

2.  <span data-ttu-id="8740e-172">Solicite uma renovação ou um novo certificado OAuthTokenIssuer com a chave privada exportável para o certificado existente no serviço de borda A/V.</span><span class="sxs-lookup"><span data-stu-id="8740e-172">Request a renewal or new OAuthTokenIssuer certificate with exportable private key for the existing certificate on the A/V Edge service.</span></span>

3.  <span data-ttu-id="8740e-173">Importe o novo certificado OAuthTokenIssuer para um servidor front-end em seu pool (se você tiver um pool implantado).</span><span class="sxs-lookup"><span data-stu-id="8740e-173">Import the new OAuthTokenIssuer certificate to a Front End Server in your pool (if you have a pool deployed).</span></span> <span data-ttu-id="8740e-174">O certificado OAuthTokenIssuer é replicado globalmente e só precisa ser atualizado e renovado em qualquer servidor em sua implantação.</span><span class="sxs-lookup"><span data-stu-id="8740e-174">The OAuthTokenIssuer certificate is replicated globally and only needs to be updated and renewed at any server in your deployment.</span></span> <span data-ttu-id="8740e-175">O servidor front-end é usado como um exemplo.</span><span class="sxs-lookup"><span data-stu-id="8740e-175">The Front End Server is used as an example.</span></span>

4.  <span data-ttu-id="8740e-176">Configure o certificado importado com o cmdlet Set-CsCertificate e use o parâmetro – rolo com o parâmetro – EffectiveDate.</span><span class="sxs-lookup"><span data-stu-id="8740e-176">Configure the imported certificate with the Set-CsCertificate cmdlet and use the –Roll parameter with the –EffectiveDate parameter.</span></span> <span data-ttu-id="8740e-177">A data efetiva deve ser definida como o tempo de expiração do certificado atual (14:00:00 ou 2:00:00 PM) menos de 24 horas.</span><span class="sxs-lookup"><span data-stu-id="8740e-177">The effective date should be defined as the current certificate expire time (14:00:00, or 2:00:00 PM) minus a minimum of 24 hours.</span></span>
    
    <span data-ttu-id="8740e-178">O comando Set-CsCertificate com o parâmetro – rolo e – effectiveTime:</span><span class="sxs-lookup"><span data-stu-id="8740e-178">The Set-CsCertificate command with the –Roll and –EffectiveTime parameter:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb print of new certificate> -Roll -EffectiveDate <date and time for certificate to become active>
    
    <span data-ttu-id="8740e-179">Um exemplo Set-CsCertificate comando:</span><span class="sxs-lookup"><span data-stu-id="8740e-179">An example Set-CsCertificate command:</span></span>
    
        Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2012 1:00:00 PM"
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="8740e-180">O EffectiveDate deve ser formatado para corresponder às configurações de idioma e região do seu servidor.</span><span class="sxs-lookup"><span data-stu-id="8740e-180">The EffectiveDate must be formatted to match your server’s region and language settings.</span></span> <span data-ttu-id="8740e-181">O exemplo usa as configurações de idioma e região inglês dos EUA</span><span class="sxs-lookup"><span data-stu-id="8740e-181">The example uses the US English Region and Language settings</span></span>

    
    </div>

<span data-ttu-id="8740e-182">Quando a hora efetiva é atingida (7/21/2012 1:00:00 AM), todos os novos tokens são emitidos pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-182">When the effective time is reached (7/21/2012 1:00:00 AM), all new tokens are issued by the new certificate.</span></span> <span data-ttu-id="8740e-183">Ao validar tokens, os tokens serão validados primeiro em relação ao novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-183">When validating tokens, tokens will first be validated against the new certificate.</span></span> <span data-ttu-id="8740e-184">Se a validação falhar, o certificado antigo será tentado.</span><span class="sxs-lookup"><span data-stu-id="8740e-184">If the validation fails, the old certificate is tried.</span></span> <span data-ttu-id="8740e-185">O processo de experimentar o novo e retornar ao certificado antigo continuará até o tempo de expiração do certificado antigo.</span><span class="sxs-lookup"><span data-stu-id="8740e-185">The process of trying the new and falling back to the old certificate will continue until the expiry time of the old certificate.</span></span> <span data-ttu-id="8740e-186">Quando o certificado antigo expirar (7/22/2012 2:00:00 PM), os tokens serão validados apenas pelo novo certificado.</span><span class="sxs-lookup"><span data-stu-id="8740e-186">Once the old certificate has expired (7/22/2012 2:00:00 PM), tokens will only be validated by the new certificate.</span></span> <span data-ttu-id="8740e-187">O certificado antigo pode ser removido com segurança usando o cmdlet Remove-CsCertificate com o parâmetro – Previous.</span><span class="sxs-lookup"><span data-stu-id="8740e-187">The old certificate can be safely removed using the Remove-CsCertificate cmdlet with the –Previous parameter.</span></span>

    Remove-CsCertificate -Type OAuthTokenIssuer -Previous

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8740e-188">Confira também</span><span class="sxs-lookup"><span data-stu-id="8740e-188">See Also</span></span>


[<span data-ttu-id="8740e-189">Planejar certificados de servidor de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8740e-189">Plan for Edge Server certificates in Lync Server 2013</span></span>](lync-server-2013-plan-for-edge-server-certificates.md)  
[<span data-ttu-id="8740e-190">Gerenciando a autenticação de servidor para servidor (OAuth) e aplicativos de parceiros no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8740e-190">Managing server-to-server authentication (OAuth) and partner applications in Lync Server 2013</span></span>](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)  


[<span data-ttu-id="8740e-191">Configurar certificados de borda para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8740e-191">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)  
<span data-ttu-id="8740e-192">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8740e-192">[Set-CsCertificate](https://technet.microsoft.com/library/Gg398518(v=OCS.15))</span></span>  
<span data-ttu-id="8740e-193">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="8740e-193">[Remove-CsCertificate](https://technet.microsoft.com/library/Gg412895(v=OCS.15))</span></span>  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

