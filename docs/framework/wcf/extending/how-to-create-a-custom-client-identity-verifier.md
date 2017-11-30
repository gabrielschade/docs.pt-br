---
title: Como criar um verificador de identidade de cliente personalizado
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: f2d34e43-fa8b-46d2-91cf-d2960e13e16b
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 75200cc6aca424befe068a9dd718c6cc76492a91
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-custom-client-identity-verifier"></a><span data-ttu-id="ca6c5-102">Como criar um verificador de identidade de cliente personalizado</span><span class="sxs-lookup"><span data-stu-id="ca6c5-102">How to: Create a Custom Client Identity Verifier</span></span>
<span data-ttu-id="ca6c5-103">O *identidade* recurso de [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] permite que o cliente especificar com antecedência a identidade esperada do serviço.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-103">The *identity* feature of [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] enables a client to specify in advance the expected identity of the service.</span></span> <span data-ttu-id="ca6c5-104">Sempre que um servidor autentica o cliente, a identidade é verificada em relação a identidade esperada.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-104">Whenever a server authenticates itself to the client, the identity is checked against the expected identity.</span></span> <span data-ttu-id="ca6c5-105">(Para obter uma explicação de identidade e como ele funciona, consulte [autenticação e identidade de serviço](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span><span class="sxs-lookup"><span data-stu-id="ca6c5-105">(For an explanation of identity and how it works, see [Service Identity and Authentication](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).)</span></span>  
  
 <span data-ttu-id="ca6c5-106">Se necessário, a verificação pode ser personalizada usando um verificador de identidade personalizada.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-106">If needed, the verification can be customized using a custom identity verifier.</span></span> <span data-ttu-id="ca6c5-107">Por exemplo, você pode executar operações de verificação de identidade de serviço adicional.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-107">For example, you can perform additional service identity verification checks.</span></span> <span data-ttu-id="ca6c5-108">Neste exemplo, o verificador de identidade personalizado verifica declarações adicionais no certificado x. 509 retornada do servidor.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-108">In this example, the custom identity verifier checks additional claims in the X.509 certificate returned from the server.</span></span> <span data-ttu-id="ca6c5-109">Para um aplicativo de exemplo, consulte [exemplo de identidade de serviço](../../../../docs/framework/wcf/samples/service-identity-sample.md).</span><span class="sxs-lookup"><span data-stu-id="ca6c5-109">For a sample application, see [Service Identity Sample](../../../../docs/framework/wcf/samples/service-identity-sample.md).</span></span>  
  
### <a name="to-extend-the-endpointidentity-class"></a><span data-ttu-id="ca6c5-110">Estender a classe EndpointIdentity</span><span class="sxs-lookup"><span data-stu-id="ca6c5-110">To extend the EndpointIdentity class</span></span>  
  
1.  <span data-ttu-id="ca6c5-111">Definir uma nova classe que deriva de <xref:System.ServiceModel.EndpointIdentity> classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-111">Define a new class that derives from the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="ca6c5-112">Este exemplo denomina a extensão `OrgEndpointIdentity`.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-112">This example names the extension `OrgEndpointIdentity`.</span></span>  
  
2.  <span data-ttu-id="ca6c5-113">Adicionar membros particulares junto com propriedades que serão usados pelo estendido <xref:System.ServiceModel.Security.IdentityVerifier> classe para executar a verificação de identidade nas declarações no token de segurança retornado do serviço.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-113">Add private members along with properties that will be used by the extended <xref:System.ServiceModel.Security.IdentityVerifier> class to perform the identity check against claims in the security token returned from the service.</span></span> <span data-ttu-id="ca6c5-114">Este exemplo define uma propriedade: o `OrganizationClaim` propriedade.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-114">This example defines one property: the `OrganizationClaim` property.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
     [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
### <a name="to-extend-the-identityverifier-class"></a><span data-ttu-id="ca6c5-115">Estender a classe IdentityVerifier</span><span class="sxs-lookup"><span data-stu-id="ca6c5-115">To extend the IdentityVerifier class</span></span>  
  
1.  <span data-ttu-id="ca6c5-116">Definir uma nova classe que deriva de <xref:System.ServiceModel.Security.IdentityVerifier>.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-116">Define a new class that derives from <xref:System.ServiceModel.Security.IdentityVerifier>.</span></span> <span data-ttu-id="ca6c5-117">Este exemplo denomina a extensão `CustomIdentityVerifier`.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-117">This example names the extension `CustomIdentityVerifier`.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#7)]
     [!code-vb[c_HowToSetCustomClientIdentity#7](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#7)]  
  
2.  <span data-ttu-id="ca6c5-118">Substituir o método <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A>.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-118">Override the <xref:System.ServiceModel.Security.IdentityVerifier.CheckAccess%2A> method.</span></span> <span data-ttu-id="ca6c5-119">O método determina se a verificação de identidade teve êxito ou falha.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-119">The method determines whether the identity check succeeded or failed.</span></span>  
  
3.  <span data-ttu-id="ca6c5-120">O `CheckAccess` método tem dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-120">The `CheckAccess` method has two parameters.</span></span> <span data-ttu-id="ca6c5-121">A primeira é uma ocorrência da <xref:System.ServiceModel.EndpointIdentity> classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-121">The first is an instance of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span> <span data-ttu-id="ca6c5-122">O segundo é uma ocorrência da <xref:System.IdentityModel.Policy.AuthorizationContext> classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-122">The second is an instance of the <xref:System.IdentityModel.Policy.AuthorizationContext> class.</span></span>  
  
     <span data-ttu-id="ca6c5-123">Na implementação do método, examine a coleção de declarações retornado pelo <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> propriedade o <xref:System.IdentityModel.Policy.AuthorizationContext> de classe e executar verificações de autenticação conforme necessário.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-123">In the method implementation, examine the collection of claims returned by the <xref:System.IdentityModel.Policy.AuthorizationContext.ClaimSets%2A> property of the <xref:System.IdentityModel.Policy.AuthorizationContext> class, and perform authentication checks as required.</span></span> <span data-ttu-id="ca6c5-124">Este exemplo inicia Localizando qualquer declaração que é do tipo "Nome distinto" e, em seguida, compara o nome para a extensão do <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span><span class="sxs-lookup"><span data-stu-id="ca6c5-124">This example begins by finding any claim that is of type "Distinguished Name" and then compares the name to the extension of the <xref:System.ServiceModel.EndpointIdentity> (`OrgEndpointIdentity`).</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#1)]
     [!code-vb[c_HowToSetCustomClientIdentity#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#1)]  
  
### <a name="to-implement-the-trygetidentity-method"></a><span data-ttu-id="ca6c5-125">Para implementar o método TryGetIdentity</span><span class="sxs-lookup"><span data-stu-id="ca6c5-125">To implement the TryGetIdentity method</span></span>  
  
1.  <span data-ttu-id="ca6c5-126">Implementar o <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> método, que determina se uma instância do <xref:System.ServiceModel.EndpointIdentity> classe pode ser retornada pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-126">Implement the <xref:System.ServiceModel.Security.IdentityVerifier.TryGetIdentity%2A> method, which determines whether an instance of the <xref:System.ServiceModel.EndpointIdentity> class can be returned by the client.</span></span> <span data-ttu-id="ca6c5-127">O [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infraestrutura chama a implementação do `TryGetIdentity` método primeiro para recuperar a identidade do serviço de mensagem.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-127">The [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure calls the implementation of the `TryGetIdentity` method first to retrieve the service's identity from the message.</span></span> <span data-ttu-id="ca6c5-128">Em seguida, chama a infraestrutura de `CheckAccess` implementação de com retornado `EndpointIdentity` e <xref:System.IdentityModel.Policy.AuthorizationContext>.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-128">Next, the infrastructure calls the `CheckAccess` implementation with the returned `EndpointIdentity` and <xref:System.IdentityModel.Policy.AuthorizationContext>.</span></span>  
  
2.  <span data-ttu-id="ca6c5-129">No `TryGetIdentity` método, coloque o seguinte código:</span><span class="sxs-lookup"><span data-stu-id="ca6c5-129">In the `TryGetIdentity` method, put the following code:</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#2)]
     [!code-vb[c_HowToSetCustomClientIdentity#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#2)]  
  
### <a name="to-implement-a-custom-binding-and-set-the-custom-identityverifier"></a><span data-ttu-id="ca6c5-130">Para implementar uma associação personalizada e definir o IdentityVerifier personalizado</span><span class="sxs-lookup"><span data-stu-id="ca6c5-130">To implement a custom binding and set the custom IdentityVerifier</span></span>  
  
1.  <span data-ttu-id="ca6c5-131">Criar um método que retorna um <xref:System.ServiceModel.Channels.Binding> objeto.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-131">Create a method that returns a <xref:System.ServiceModel.Channels.Binding> object.</span></span> <span data-ttu-id="ca6c5-132">Este exemplo inicia cria uma instância do <xref:System.ServiceModel.WSHttpBinding> classe e define o modo de segurança para <xref:System.ServiceModel.SecurityMode.Message>e sua <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> para <xref:System.ServiceModel.MessageCredentialType.None>.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-132">This example begins creates an instance of the <xref:System.ServiceModel.WSHttpBinding> class and sets its security mode to <xref:System.ServiceModel.SecurityMode.Message>, and its <xref:System.ServiceModel.MessageSecurityOverHttp.ClientCredentialType%2A> to <xref:System.ServiceModel.MessageCredentialType.None>.</span></span>  
  
2.  <span data-ttu-id="ca6c5-133">Criar um <xref:System.ServiceModel.Channels.BindingElementCollection> usando o <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> método.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-133">Create a <xref:System.ServiceModel.Channels.BindingElementCollection> using the <xref:System.ServiceModel.WSHttpBinding.CreateBindingElements%2A> method.</span></span>  
  
3.  <span data-ttu-id="ca6c5-134">Retornar o <xref:System.ServiceModel.Channels.SecurityBindingElement> da coleção e convertê-lo para um <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variável.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-134">Return the <xref:System.ServiceModel.Channels.SecurityBindingElement> from the collection and cast it to a <xref:System.ServiceModel.Channels.SymmetricSecurityBindingElement> variable.</span></span>  
  
4.  <span data-ttu-id="ca6c5-135">Definir o <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> propriedade do <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> uma nova instância da classe de `CustomIdentityVerifier` classe criada anteriormente.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-135">Set the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings.IdentityVerifier%2A> property of the <xref:System.ServiceModel.Channels.LocalClientSecuritySettings> class to a new instance of the `CustomIdentityVerifier` class created previously.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#3)]
     [!code-vb[c_HowToSetCustomClientIdentity#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#3)]  
  
5.  <span data-ttu-id="ca6c5-136">A associação personalizada que é retornada é usada para criar uma instância do cliente e da classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-136">The custom binding that is returned is used to create an instance of the client and class.</span></span> <span data-ttu-id="ca6c5-137">O cliente, em seguida, pode executar uma verificação de identidade personalizado do serviço, conforme mostrado no código a seguir.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-137">The client can then perform a custom identity verification check of the service as shown in the following code.</span></span>  
  
     [!code-csharp[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#4)]
     [!code-vb[c_HowToSetCustomClientIdentity#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#4)]  
  
## <a name="example"></a><span data-ttu-id="ca6c5-138">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ca6c5-138">Example</span></span>  
 <span data-ttu-id="ca6c5-139">O exemplo a seguir mostra uma implementação completa de <xref:System.ServiceModel.Security.IdentityVerifier> classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-139">The following example shows a complete implementation of the <xref:System.ServiceModel.Security.IdentityVerifier> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#5)]
 [!code-vb[c_HowToSetCustomClientIdentity#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#5)]  
  
## <a name="example"></a><span data-ttu-id="ca6c5-140">Exemplo</span><span class="sxs-lookup"><span data-stu-id="ca6c5-140">Example</span></span>  
 <span data-ttu-id="ca6c5-141">O exemplo a seguir mostra uma implementação completa de <xref:System.ServiceModel.EndpointIdentity> classe.</span><span class="sxs-lookup"><span data-stu-id="ca6c5-141">The following example shows a complete implementation of the <xref:System.ServiceModel.EndpointIdentity> class.</span></span>  
  
 [!code-csharp[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howtosetcustomclientidentity/cs/source.cs#6)]
 [!code-vb[c_HowToSetCustomClientIdentity#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howtosetcustomclientidentity/vb/source.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ca6c5-142">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ca6c5-142">See Also</span></span>  
 <xref:System.ServiceModel.ServiceAuthorizationManager>  
 <xref:System.ServiceModel.EndpointIdentity>  
 <xref:System.ServiceModel.Security.IdentityVerifier>  
 [<span data-ttu-id="ca6c5-143">Exemplo de identidade de serviço</span><span class="sxs-lookup"><span data-stu-id="ca6c5-143">Service Identity Sample</span></span>](../../../../docs/framework/wcf/samples/service-identity-sample.md)  
 [<span data-ttu-id="ca6c5-144">Política de autorização</span><span class="sxs-lookup"><span data-stu-id="ca6c5-144">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)  
 [<span data-ttu-id="ca6c5-145">Política de autorização</span><span class="sxs-lookup"><span data-stu-id="ca6c5-145">Authorization Policy</span></span>](../../../../docs/framework/wcf/samples/authorization-policy.md)