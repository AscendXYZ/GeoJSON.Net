[![ascend MyGet Build Status](https://www.myget.org/BuildSource/Badge/ascend?identifier=bba86624-b8cc-4a25-b7ed-ce127fe8da30)](https://www.myget.org/)

##What is GeoJSON.NET
GeoJSON is .NET library for the GeoJSON spec v1.0 (see http://geojson.org/geojson-spec.html), it uses Newtonsoft Json.NET (http://json.codeplex.com) for serialization and deserialization.

##Installing
1. Available as NuGet package via 'Install-Package GeoJSON.Net', see https://nuget.org/packages/GeoJSON.Net
2. Download the source, compile and include GeoJSON.Net.dll in you project

##Examples
### Point serialization
    `var point = new GeoJSON.Net.Geometry.Point(new GeoJSON.Net.Geometry.GeographicPosition(45.79012, 15.94107));
	var featureProperties = new Dictionary<string, object> { {"Name", "Foo"} };
	var model = new GeoJSON.Net.Feature.Feature(point, featureProperties);
	var serializedData = JsonConvert.SerializeObject(model, Formatting.Indented, new JsonSerializerSettings { ContractResolver = new CamelCasePropertyNamesContractResolver(), NullValueHandling = NullValueHandling.Ignore });`

### Deserialize GeoJSON file  
    `JsonConvert.DeserializeObject<GeoJSON.Net.Feature.FeatureCollection>(string content);`

##News
- 2014-06-25 - added Polygon and Point serialization

Enjoy!  
-Joerg Battermann  
jb at joergbattermann.com
