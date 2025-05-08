( () => {
    "use strict";
    var e = {
        769: function(e, t, r) {
            t.validateByProduct = t.getIssueMetadataMap = void 0;
            var a = r(1378);
            Object.defineProperty(t, "getIssueMetadataMap", {
                enumerable: !0,
                get: function() {
                    return a.getIssueMetadataMap
                }
            });
            var s = r(2254);
            Object.defineProperty(t, "validateByProduct", {
                enumerable: !0,
                get: function() {
                    return s.validateByProduct
                }
            })
        },
        833: function(e, t) {
            Object.defineProperty(t, "__esModule", {
                value: !0
            }),
            t.customValidatorMap = void 0,
            t.customValidatorMap = {}
        },
        6256: function(e, t, r) {
            var a = this && this.__importDefault || function(e) {
                return e && e.__esModule ? e : {
                    default: e
                }
            }
            ;
            Object.defineProperty(t, "__esModule", {
                value: !0
            }),
            t.getJsonSchemaValidateMap = void 0;
            var s = a(r(2305));
            t.getJsonSchemaValidateMap = function() {
                return s.default
            }
        },
        2305: function(e, t, r) {
            t.EMPTY_EVENT_TYPE_NAME = n;
            let a = {
                $schema: "/draft-07/schema#",
                $id: "EMPTY_EVENT_TYPE_NAME",
                title: "EMPTY_EVENT_TYPE_NAME issue",
                type: "object",
                properties: {
                    event: {
                        not: {
                            pattern: "^\\s*$"
                        }
                    }
                },
                required: ["event"]
            }
              , s = RegExp("^\\s*$", "u");
            function n(e, {instancePath: t="", parentData: r, parentDataProperty: i, rootData: o=e}={}) {
                let p = null
                  , l = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return n.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: a.type,
                        parentSchema: a,
                        data: e
                    }],
                    !1;
                {
                    let r;
                    if (void 0 === e.event && (r = "event"))
                        return n.errors = [{
                            instancePath: t,
                            schemaPath: "#/required",
                            keyword: "required",
                            params: {
                                missingProperty: r
                            },
                            message: "must have required property '" + r + "'",
                            schema: a.required,
                            parentSchema: a,
                            data: e
                        }],
                        !1;
                    if (void 0 !== e.event) {
                        let r = e.event
                          , i = l
                          , o = l;
                        if ("string" == typeof r && !s.test(r)) {
                            let e = {};
                            null === p ? p = [e] : p.push(e),
                            l++
                        }
                        if (o === l)
                            return n.errors = [{
                                instancePath: t + "/event",
                                schemaPath: "#/properties/event/not",
                                keyword: "not",
                                params: {},
                                message: "must NOT be valid",
                                schema: a.properties.event.not,
                                parentSchema: a.properties.event,
                                data: r
                            }],
                            !1;
                        l = i,
                        null !== p && (i ? p.length = i : p = null)
                    }
                }
                return n.errors = p,
                0 === l
            }
            t.INVALID_CONTENT_ID = y;
            let i = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_CONTENT_ID",
                title: "INVALID_CONTENT_ID issue",
                type: "object",
                if: {
                    properties: {
                        event: {
                            $ref: "#/$defs/ecomEvent"
                        }
                    },
                    required: ["event"]
                },
                then: {
                    properties: {
                        properties: {
                            type: "object",
                            allOf: [{
                                $ref: "#/$defs/singleProduct"
                            }, {
                                $ref: "#/$defs/multiProducts"
                            }]
                        }
                    }
                },
                $defs: {
                    content_id: {
                        anyOf: [{
                            type: "string",
                            minLength: 1,
                            not: {
                                pattern: "^\\s*$"
                            }
                        }, {
                            type: "number"
                        }]
                    },
                    content_ids: {
                        anyOf: [{
                            $ref: "#/$defs/content_id"
                        }, {
                            type: "array",
                            items: {
                                $ref: "#/$defs/content_id"
                            }
                        }]
                    },
                    ecomEvent: {
                        type: "string",
                        enum: ["CompletePayment", "InitiateCheckout", "AddToCart", "PlaceAnOrder", "ViewContent", "AddToWishlist"]
                    },
                    singleProduct: {
                        type: "object",
                        properties: {
                            content_id: {
                                $ref: "#/$defs/content_id"
                            },
                            content_ids: {
                                $ref: "#/$defs/content_ids"
                            }
                        }
                    },
                    multiProducts: {
                        type: "object",
                        properties: {
                            contents: {
                                type: "array",
                                items: {
                                    properties: {
                                        content_id: {
                                            $ref: "#/$defs/content_id"
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            }
              , o = {
                type: "object",
                properties: {
                    content_id: {
                        $ref: "#/$defs/content_id"
                    },
                    content_ids: {
                        $ref: "#/$defs/content_ids"
                    }
                }
            }
              , p = {
                anyOf: [{
                    type: "string",
                    minLength: 1,
                    not: {
                        pattern: "^\\s*$"
                    }
                }, {
                    type: "number"
                }]
            }
              , l = r(7055).default
              , c = {
                anyOf: [{
                    $ref: "#/$defs/content_id"
                }, {
                    type: "array",
                    items: {
                        $ref: "#/$defs/content_id"
                    }
                }]
            };
            function h(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: n=e}={}) {
                let i = null
                  , o = 0
                  , u = !1
                  , d = !1;
                if ("string" == typeof e && !s.test(e)) {
                    let e = {};
                    null === i ? i = [e] : i.push(e),
                    o++
                }
                if (0 === o) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/$defs/content_id/anyOf/0/not",
                        keyword: "not",
                        params: {},
                        message: "must NOT be valid",
                        schema: p.anyOf[0].not,
                        parentSchema: p.anyOf[0],
                        data: e
                    };
                    null === i ? i = [r] : i.push(r),
                    o++
                } else
                    o = 0,
                    null !== i && (i = null);
                if (0 === o)
                    if ("string" == typeof e) {
                        if (1 > l(e)) {
                            let r = {
                                instancePath: t,
                                schemaPath: "#/$defs/content_id/anyOf/0/minLength",
                                keyword: "minLength",
                                params: {
                                    limit: 1
                                },
                                message: "must NOT have fewer than 1 characters",
                                schema: 1,
                                parentSchema: p.anyOf[0],
                                data: e
                            };
                            null === i ? i = [r] : i.push(r),
                            o++
                        }
                    } else {
                        let r = {
                            instancePath: t,
                            schemaPath: "#/$defs/content_id/anyOf/0/type",
                            keyword: "type",
                            params: {
                                type: "string"
                            },
                            message: "must be string",
                            schema: p.anyOf[0].type,
                            parentSchema: p.anyOf[0],
                            data: e
                        };
                        null === i ? i = [r] : i.push(r),
                        o++
                    }
                var m = 0 === o;
                if (!(d = d || m)) {
                    let r = o;
                    if ("number" != typeof e) {
                        let r = {
                            instancePath: t,
                            schemaPath: "#/$defs/content_id/anyOf/1/type",
                            keyword: "type",
                            params: {
                                type: "number"
                            },
                            message: "must be number",
                            schema: p.anyOf[1].type,
                            parentSchema: p.anyOf[1],
                            data: e
                        };
                        null === i ? i = [r] : i.push(r),
                        o++
                    }
                    var m = r === o;
                    d = d || m
                }
                if (d)
                    o = 0,
                    null !== i && (i = null);
                else {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/$defs/content_id/anyOf",
                        keyword: "anyOf",
                        params: {},
                        message: "must match a schema in anyOf",
                        schema: p.anyOf,
                        parentSchema: p,
                        data: e
                    };
                    null === i ? i = [r] : i.push(r),
                    o++
                }
                var y = 0 === o;
                if (!(u = u || y)) {
                    let r = o;
                    if (o === r)
                        if (Array.isArray(e)) {
                            var f = !0;
                            let r = e.length;
                            for (let a = 0; a < r; a++) {
                                let r = e[a]
                                  , n = o
                                  , c = o
                                  , h = !1
                                  , u = o
                                  , d = o
                                  , m = o;
                                if ("string" == typeof r && !s.test(r)) {
                                    let e = {};
                                    null === i ? i = [e] : i.push(e),
                                    o++
                                }
                                if (m === o) {
                                    let e = {
                                        instancePath: t + "/" + a,
                                        schemaPath: "#/$defs/content_id/anyOf/0/not",
                                        keyword: "not",
                                        params: {},
                                        message: "must NOT be valid",
                                        schema: p.anyOf[0].not,
                                        parentSchema: p.anyOf[0],
                                        data: r
                                    };
                                    null === i ? i = [e] : i.push(e),
                                    o++
                                } else
                                    o = d,
                                    null !== i && (d ? i.length = d : i = null);
                                if (o === u)
                                    if ("string" == typeof r) {
                                        if (1 > l(r)) {
                                            let e = {
                                                instancePath: t + "/" + a,
                                                schemaPath: "#/$defs/content_id/anyOf/0/minLength",
                                                keyword: "minLength",
                                                params: {
                                                    limit: 1
                                                },
                                                message: "must NOT have fewer than 1 characters",
                                                schema: 1,
                                                parentSchema: p.anyOf[0],
                                                data: r
                                            };
                                            null === i ? i = [e] : i.push(e),
                                            o++
                                        }
                                    } else {
                                        let e = {
                                            instancePath: t + "/" + a,
                                            schemaPath: "#/$defs/content_id/anyOf/0/type",
                                            keyword: "type",
                                            params: {
                                                type: "string"
                                            },
                                            message: "must be string",
                                            schema: p.anyOf[0].type,
                                            parentSchema: p.anyOf[0],
                                            data: r
                                        };
                                        null === i ? i = [e] : i.push(e),
                                        o++
                                    }
                                var _ = u === o;
                                if (!(h = h || _)) {
                                    let e = o;
                                    if ("number" != typeof r) {
                                        let e = {
                                            instancePath: t + "/" + a,
                                            schemaPath: "#/$defs/content_id/anyOf/1/type",
                                            keyword: "type",
                                            params: {
                                                type: "number"
                                            },
                                            message: "must be number",
                                            schema: p.anyOf[1].type,
                                            parentSchema: p.anyOf[1],
                                            data: r
                                        };
                                        null === i ? i = [e] : i.push(e),
                                        o++
                                    }
                                    var _ = e === o;
                                    h = h || _
                                }
                                if (h)
                                    o = c,
                                    null !== i && (c ? i.length = c : i = null);
                                else {
                                    let e = {
                                        instancePath: t + "/" + a,
                                        schemaPath: "#/$defs/content_id/anyOf",
                                        keyword: "anyOf",
                                        params: {},
                                        message: "must match a schema in anyOf",
                                        schema: p.anyOf,
                                        parentSchema: p,
                                        data: r
                                    };
                                    null === i ? i = [e] : i.push(e),
                                    o++
                                }
                                var f = n === o;
                                if (!f)
                                    break
                            }
                        } else {
                            let r = {
                                instancePath: t,
                                schemaPath: "#/anyOf/1/type",
                                keyword: "type",
                                params: {
                                    type: "array"
                                },
                                message: "must be array",
                                schema: c.anyOf[1].type,
                                parentSchema: c.anyOf[1],
                                data: e
                            };
                            null === i ? i = [r] : i.push(r),
                            o++
                        }
                    var y = r === o;
                    u = u || y
                }
                if (u)
                    o = 0,
                    null !== i && (i = null);
                else {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/anyOf",
                        keyword: "anyOf",
                        params: {},
                        message: "must match a schema in anyOf",
                        schema: c.anyOf,
                        parentSchema: c,
                        data: e
                    };
                    return null === i ? i = [r] : i.push(r),
                    o++,
                    h.errors = i,
                    !1
                }
                return h.errors = i,
                0 === o
            }
            function u(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: n=e}={}) {
                let i = null
                  , c = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return u.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: o.type,
                        parentSchema: o,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.content_id) {
                    let r = e.content_id
                      , a = c
                      , n = c
                      , o = !1
                      , h = c
                      , y = c
                      , f = c;
                    if ("string" == typeof r && !s.test(r)) {
                        let e = {};
                        null === i ? i = [e] : i.push(e),
                        c++
                    }
                    if (f === c) {
                        let e = {
                            instancePath: t + "/content_id",
                            schemaPath: "#/$defs/content_id/anyOf/0/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: p.anyOf[0].not,
                            parentSchema: p.anyOf[0],
                            data: r
                        };
                        null === i ? i = [e] : i.push(e),
                        c++
                    } else
                        c = y,
                        null !== i && (y ? i.length = y : i = null);
                    if (c === h)
                        if ("string" == typeof r) {
                            if (1 > l(r)) {
                                let e = {
                                    instancePath: t + "/content_id",
                                    schemaPath: "#/$defs/content_id/anyOf/0/minLength",
                                    keyword: "minLength",
                                    params: {
                                        limit: 1
                                    },
                                    message: "must NOT have fewer than 1 characters",
                                    schema: 1,
                                    parentSchema: p.anyOf[0],
                                    data: r
                                };
                                null === i ? i = [e] : i.push(e),
                                c++
                            }
                        } else {
                            let e = {
                                instancePath: t + "/content_id",
                                schemaPath: "#/$defs/content_id/anyOf/0/type",
                                keyword: "type",
                                params: {
                                    type: "string"
                                },
                                message: "must be string",
                                schema: p.anyOf[0].type,
                                parentSchema: p.anyOf[0],
                                data: r
                            };
                            null === i ? i = [e] : i.push(e),
                            c++
                        }
                    var d = h === c;
                    if (!(o = o || d)) {
                        let e = c;
                        if ("number" != typeof r) {
                            let e = {
                                instancePath: t + "/content_id",
                                schemaPath: "#/$defs/content_id/anyOf/1/type",
                                keyword: "type",
                                params: {
                                    type: "number"
                                },
                                message: "must be number",
                                schema: p.anyOf[1].type,
                                parentSchema: p.anyOf[1],
                                data: r
                            };
                            null === i ? i = [e] : i.push(e),
                            c++
                        }
                        var d = e === c;
                        o = o || d
                    }
                    if (o)
                        c = n,
                        null !== i && (n ? i.length = n : i = null);
                    else {
                        let e = {
                            instancePath: t + "/content_id",
                            schemaPath: "#/$defs/content_id/anyOf",
                            keyword: "anyOf",
                            params: {},
                            message: "must match a schema in anyOf",
                            schema: p.anyOf,
                            parentSchema: p,
                            data: r
                        };
                        return null === i ? i = [e] : i.push(e),
                        c++,
                        u.errors = i,
                        !1
                    }
                    var m = a === c
                } else
                    var m = !0;
                if (m)
                    if (void 0 !== e.content_ids) {
                        let r = c;
                        h(e.content_ids, {
                            instancePath: t + "/content_ids",
                            parentData: e,
                            parentDataProperty: "content_ids",
                            rootData: n
                        }) || (c = (i = null === i ? h.errors : i.concat(h.errors)).length);
                        var m = r === c
                    } else
                        var m = !0;
                return u.errors = i,
                0 === c
            }
            let d = {
                type: "object",
                properties: {
                    contents: {
                        type: "array",
                        items: {
                            properties: {
                                content_id: {
                                    $ref: "#/$defs/content_id"
                                }
                            }
                        }
                    }
                }
            };
            function m(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: n=e}={}) {
                let i = null
                  , o = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return m.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: d.type,
                        parentSchema: d,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.contents) {
                    let r = e.contents
                      , a = o;
                    if (o === a)
                        if (!Array.isArray(r))
                            return m.errors = [{
                                instancePath: t + "/contents",
                                schemaPath: "#/properties/contents/type",
                                keyword: "type",
                                params: {
                                    type: "array"
                                },
                                message: "must be array",
                                schema: d.properties.contents.type,
                                parentSchema: d.properties.contents,
                                data: r
                            }],
                            !1;
                        else {
                            var c = !0;
                            let e = r.length;
                            for (let a = 0; a < e; a++) {
                                let e = r[a]
                                  , n = o;
                                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.content_id) {
                                    let r = e.content_id
                                      , n = o
                                      , c = !1
                                      , u = o
                                      , d = o
                                      , y = o;
                                    if ("string" == typeof r && !s.test(r)) {
                                        let e = {};
                                        null === i ? i = [e] : i.push(e),
                                        o++
                                    }
                                    if (y === o) {
                                        let e = {
                                            instancePath: t + "/contents/" + a + "/content_id",
                                            schemaPath: "#/$defs/content_id/anyOf/0/not",
                                            keyword: "not",
                                            params: {},
                                            message: "must NOT be valid",
                                            schema: p.anyOf[0].not,
                                            parentSchema: p.anyOf[0],
                                            data: r
                                        };
                                        null === i ? i = [e] : i.push(e),
                                        o++
                                    } else
                                        o = d,
                                        null !== i && (d ? i.length = d : i = null);
                                    if (o === u)
                                        if ("string" == typeof r) {
                                            if (1 > l(r)) {
                                                let e = {
                                                    instancePath: t + "/contents/" + a + "/content_id",
                                                    schemaPath: "#/$defs/content_id/anyOf/0/minLength",
                                                    keyword: "minLength",
                                                    params: {
                                                        limit: 1
                                                    },
                                                    message: "must NOT have fewer than 1 characters",
                                                    schema: 1,
                                                    parentSchema: p.anyOf[0],
                                                    data: r
                                                };
                                                null === i ? i = [e] : i.push(e),
                                                o++
                                            }
                                        } else {
                                            let e = {
                                                instancePath: t + "/contents/" + a + "/content_id",
                                                schemaPath: "#/$defs/content_id/anyOf/0/type",
                                                keyword: "type",
                                                params: {
                                                    type: "string"
                                                },
                                                message: "must be string",
                                                schema: p.anyOf[0].type,
                                                parentSchema: p.anyOf[0],
                                                data: r
                                            };
                                            null === i ? i = [e] : i.push(e),
                                            o++
                                        }
                                    var h = u === o;
                                    if (!(c = c || h)) {
                                        let e = o;
                                        if ("number" != typeof r) {
                                            let e = {
                                                instancePath: t + "/contents/" + a + "/content_id",
                                                schemaPath: "#/$defs/content_id/anyOf/1/type",
                                                keyword: "type",
                                                params: {
                                                    type: "number"
                                                },
                                                message: "must be number",
                                                schema: p.anyOf[1].type,
                                                parentSchema: p.anyOf[1],
                                                data: r
                                            };
                                            null === i ? i = [e] : i.push(e),
                                            o++
                                        }
                                        var h = e === o;
                                        c = c || h
                                    }
                                    if (c)
                                        o = n,
                                        null !== i && (n ? i.length = n : i = null);
                                    else {
                                        let e = {
                                            instancePath: t + "/contents/" + a + "/content_id",
                                            schemaPath: "#/$defs/content_id/anyOf",
                                            keyword: "anyOf",
                                            params: {},
                                            message: "must match a schema in anyOf",
                                            schema: p.anyOf,
                                            parentSchema: p,
                                            data: r
                                        };
                                        return null === i ? i = [e] : i.push(e),
                                        o++,
                                        m.errors = i,
                                        !1
                                    }
                                }
                                var c = n === o;
                                if (!c)
                                    break
                            }
                        }
                }
                return m.errors = i,
                0 === o
            }
            function y(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , o = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return y.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: i.type,
                        parentSchema: i,
                        data: e
                    }],
                    !1;
                let p = o
                  , l = !0
                  , c = o;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        o++
                    } else if (void 0 !== e.event) {
                        let t = e.event;
                        if ("string" != typeof t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            o++
                        }
                        if ("CompletePayment" !== t && "InitiateCheckout" !== t && "AddToCart" !== t && "PlaceAnOrder" !== t && "ViewContent" !== t && "AddToWishlist" !== t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            o++
                        }
                    }
                }
                var h = c === o;
                if (o = p,
                null !== n && (p ? n.length = p : n = null),
                h) {
                    let r = o;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                        let r = e.properties;
                        if (!(r && "object" == typeof r && !Array.isArray(r)))
                            return y.errors = [{
                                instancePath: t + "/properties",
                                schemaPath: "#/then/properties/properties/type",
                                keyword: "type",
                                params: {
                                    type: "object"
                                },
                                message: "must be object",
                                schema: i.then.properties.properties.type,
                                parentSchema: i.then.properties.properties,
                                data: r
                            }],
                            !1;
                        let a = o;
                        u(r, {
                            instancePath: t + "/properties",
                            parentData: e,
                            parentDataProperty: "properties",
                            rootData: s
                        }) || (o = (n = null === n ? u.errors : n.concat(u.errors)).length);
                        var d = a === o;
                        if (d) {
                            let a = o;
                            m(r, {
                                instancePath: t + "/properties",
                                parentData: e,
                                parentDataProperty: "properties",
                                rootData: s
                            }) || (o = (n = null === n ? m.errors : n.concat(m.errors)).length);
                            var d = a === o
                        }
                    }
                    var h = r === o;
                    l = h
                }
                if (!l) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: i.if,
                        parentSchema: i,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    o++,
                    y.errors = n,
                    !1
                }
                return y.errors = n,
                0 === o
            }
            t.INVALID_CONTENT_TYPE = I;
            let f = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_CONTENT_TYPE",
                title: "INVALID_CONTENT_TYPE issue",
                type: "object",
                if: {
                    properties: {
                        event: {
                            $ref: "#/$defs/ecomEvent"
                        }
                    },
                    required: ["event"]
                },
                then: {
                    properties: {
                        properties: {
                            type: "object",
                            allOf: [{
                                $ref: "#/$defs/singleProduct"
                            }, {
                                $ref: "#/$defs/multiProducts"
                            }]
                        }
                    }
                },
                $defs: {
                    productContentType: {
                        type: "string",
                        enum: ["product", "product_group", "destination", "hotel", "flight", "vehicle"]
                    },
                    ecomEvent: {
                        type: "string",
                        enum: ["CompletePayment", "InitiateCheckout", "AddToCart", "PlaceAnOrder", "ViewContent", "AddToWishlist"]
                    },
                    singleProduct: {
                        type: "object",
                        properties: {
                            content_type: {
                                $ref: "#/$defs/productContentType"
                            }
                        }
                    },
                    multiProducts: {
                        type: "object",
                        properties: {
                            contents: {
                                type: "array",
                                items: {
                                    properties: {
                                        content_type: {
                                            $ref: "#/$defs/productContentType"
                                        }
                                    }
                                }
                            }
                        }
                    }
                }
            }
              , _ = {
                type: "object",
                properties: {
                    content_type: {
                        $ref: "#/$defs/productContentType"
                    }
                }
            }
              , g = {
                type: "string",
                enum: ["product", "product_group", "destination", "hotel", "flight", "vehicle"]
            };
            function v(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                if (!e || "object" != typeof e || Array.isArray(e))
                    return v.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: _.type,
                        parentSchema: _,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.content_type) {
                    let r = e.content_type;
                    if ("string" != typeof r)
                        return v.errors = [{
                            instancePath: t + "/content_type",
                            schemaPath: "#/$defs/productContentType/type",
                            keyword: "type",
                            params: {
                                type: "string"
                            },
                            message: "must be string",
                            schema: g.type,
                            parentSchema: g,
                            data: r
                        }],
                        !1;
                    if ("product" !== r && "product_group" !== r && "destination" !== r && "hotel" !== r && "flight" !== r && "vehicle" !== r)
                        return v.errors = [{
                            instancePath: t + "/content_type",
                            schemaPath: "#/$defs/productContentType/enum",
                            keyword: "enum",
                            params: {
                                allowedValues: g.enum
                            },
                            message: "must be equal to one of the allowed values",
                            schema: g.enum,
                            parentSchema: g,
                            data: r
                        }],
                        !1
                }
                return v.errors = null,
                !0
            }
            let E = {
                type: "object",
                properties: {
                    contents: {
                        type: "array",
                        items: {
                            properties: {
                                content_type: {
                                    $ref: "#/$defs/productContentType"
                                }
                            }
                        }
                    }
                }
            };
            function A(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                if (!e || "object" != typeof e || Array.isArray(e))
                    return A.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: E.type,
                        parentSchema: E,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.contents) {
                    let r = e.contents;
                    if (!Array.isArray(r))
                        return A.errors = [{
                            instancePath: t + "/contents",
                            schemaPath: "#/properties/contents/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: E.properties.contents.type,
                            parentSchema: E.properties.contents,
                            data: r
                        }],
                        !1;
                    {
                        let e = r.length;
                        for (let a = 0; a < e; a++) {
                            let e = r[a];
                            if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.content_type) {
                                let r = e.content_type;
                                if ("string" != typeof r)
                                    return A.errors = [{
                                        instancePath: t + "/contents/" + a + "/content_type",
                                        schemaPath: "#/$defs/productContentType/type",
                                        keyword: "type",
                                        params: {
                                            type: "string"
                                        },
                                        message: "must be string",
                                        schema: g.type,
                                        parentSchema: g,
                                        data: r
                                    }],
                                    !1;
                                if ("product" !== r && "product_group" !== r && "destination" !== r && "hotel" !== r && "flight" !== r && "vehicle" !== r)
                                    return A.errors = [{
                                        instancePath: t + "/contents/" + a + "/content_type",
                                        schemaPath: "#/$defs/productContentType/enum",
                                        keyword: "enum",
                                        params: {
                                            allowedValues: g.enum
                                        },
                                        message: "must be equal to one of the allowed values",
                                        schema: g.enum,
                                        parentSchema: g,
                                        data: r
                                    }],
                                    !1
                            }
                        }
                    }
                }
                return A.errors = null,
                !0
            }
            function I(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return I.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: f.type,
                        parentSchema: f,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else if (void 0 !== e.event) {
                        let t = e.event;
                        if ("string" != typeof t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                        if ("CompletePayment" !== t && "InitiateCheckout" !== t && "AddToCart" !== t && "PlaceAnOrder" !== t && "ViewContent" !== t && "AddToWishlist" !== t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                }
                var c = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                c) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                        let r = e.properties;
                        if (!(r && "object" == typeof r && !Array.isArray(r)))
                            return I.errors = [{
                                instancePath: t + "/properties",
                                schemaPath: "#/then/properties/properties/type",
                                keyword: "type",
                                params: {
                                    type: "object"
                                },
                                message: "must be object",
                                schema: f.then.properties.properties.type,
                                parentSchema: f.then.properties.properties,
                                data: r
                            }],
                            !1;
                        let a = i;
                        v(r, {
                            instancePath: t + "/properties",
                            parentData: e,
                            parentDataProperty: "properties",
                            rootData: s
                        }) || (i = (n = null === n ? v.errors : n.concat(v.errors)).length);
                        var h = a === i;
                        if (h) {
                            let a = i;
                            A(r, {
                                instancePath: t + "/properties",
                                parentData: e,
                                parentDataProperty: "properties",
                                rootData: s
                            }) || (i = (n = null === n ? A.errors : n.concat(A.errors)).length);
                            var h = a === i
                        }
                    }
                    var c = r === i;
                    p = c
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: f.if,
                        parentSchema: f,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    I.errors = n,
                    !1
                }
                return I.errors = n,
                0 === i
            }
            t.INVALID_CURRENCY_CODE = P;
            let N = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_CURRENCY_CODE",
                title: "INVALID_CURRENCY_CODE issue",
                type: "object",
                properties: {
                    properties: {
                        type: "object",
                        properties: {
                            currency: {
                                type: "string",
                                enum: ["AED", "ALL", "AMD", "ARS", "AUD", "AZN", "BDT", "BGN", "BHD", "BIF", "BOB", "BRL", "BYN", "CAD", "CHF", "CLP", "CNY", "COP", "CRC", "CZK", "DKK", "DOP", "DZD", "EGP", "EUR", "GBP", "GEL", "GTQ", "HKD", "HNL", "HUF", "IDR", "ILS", "INR", "IQD", "ISK", "JOD", "JPY", "KES", "KHR", "KRW", "KWD", "KZT", "LBP", "MAD", "MOP", "MXN", "MYR", "NGN", "NIO", "NOK", "NZD", "OMR", "PAB", "PEN", "PHP", "PKR", "PLN", "PYG", "QAR", "RON", "RSD", "RUB", "SAR", "SEK", "SGD", "THB", "TND", "TRY", "TWD", "TZS", "UAH", "USD", "UZS", "VES", "VND", "ZAR"]
                            }
                        }
                    }
                }
            };
            function P(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                if (!e || "object" != typeof e || Array.isArray(e))
                    return P.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: N.type,
                        parentSchema: N,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.properties) {
                    let r = e.properties;
                    if (!r || "object" != typeof r || Array.isArray(r))
                        return P.errors = [{
                            instancePath: t + "/properties",
                            schemaPath: "#/properties/properties/type",
                            keyword: "type",
                            params: {
                                type: "object"
                            },
                            message: "must be object",
                            schema: N.properties.properties.type,
                            parentSchema: N.properties.properties,
                            data: r
                        }],
                        !1;
                    if (void 0 !== r.currency) {
                        let e = r.currency;
                        if ("string" != typeof e)
                            return P.errors = [{
                                instancePath: t + "/properties/currency",
                                schemaPath: "#/properties/properties/properties/currency/type",
                                keyword: "type",
                                params: {
                                    type: "string"
                                },
                                message: "must be string",
                                schema: N.properties.properties.properties.currency.type,
                                parentSchema: N.properties.properties.properties.currency,
                                data: e
                            }],
                            !1;
                        if ("AED" !== e && "ALL" !== e && "AMD" !== e && "ARS" !== e && "AUD" !== e && "AZN" !== e && "BDT" !== e && "BGN" !== e && "BHD" !== e && "BIF" !== e && "BOB" !== e && "BRL" !== e && "BYN" !== e && "CAD" !== e && "CHF" !== e && "CLP" !== e && "CNY" !== e && "COP" !== e && "CRC" !== e && "CZK" !== e && "DKK" !== e && "DOP" !== e && "DZD" !== e && "EGP" !== e && "EUR" !== e && "GBP" !== e && "GEL" !== e && "GTQ" !== e && "HKD" !== e && "HNL" !== e && "HUF" !== e && "IDR" !== e && "ILS" !== e && "INR" !== e && "IQD" !== e && "ISK" !== e && "JOD" !== e && "JPY" !== e && "KES" !== e && "KHR" !== e && "KRW" !== e && "KWD" !== e && "KZT" !== e && "LBP" !== e && "MAD" !== e && "MOP" !== e && "MXN" !== e && "MYR" !== e && "NGN" !== e && "NIO" !== e && "NOK" !== e && "NZD" !== e && "OMR" !== e && "PAB" !== e && "PEN" !== e && "PHP" !== e && "PKR" !== e && "PLN" !== e && "PYG" !== e && "QAR" !== e && "RON" !== e && "RSD" !== e && "RUB" !== e && "SAR" !== e && "SEK" !== e && "SGD" !== e && "THB" !== e && "TND" !== e && "TRY" !== e && "TWD" !== e && "TZS" !== e && "UAH" !== e && "USD" !== e && "UZS" !== e && "VES" !== e && "VND" !== e && "ZAR" !== e)
                            return P.errors = [{
                                instancePath: t + "/properties/currency",
                                schemaPath: "#/properties/properties/properties/currency/enum",
                                keyword: "enum",
                                params: {
                                    allowedValues: N.properties.properties.properties.currency.enum
                                },
                                message: "must be equal to one of the allowed values",
                                schema: N.properties.properties.properties.currency.enum,
                                parentSchema: N.properties.properties.properties.currency,
                                data: e
                            }],
                            !1
                    }
                }
                return P.errors = null,
                !0
            }
            t.INVALID_EMAIL_FORMAT = D;
            let T = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_EMAIL_FORMAT",
                title: "INVALID_EMAIL_FORMAT issue",
                type: "object",
                if: {
                    properties: {
                        _inspection: {
                            type: "object"
                        },
                        event: {
                            type: "string",
                            not: {
                                enum: ["EnrichAM"]
                            }
                        }
                    },
                    required: ["_inspection", "event"]
                },
                then: {
                    properties: {
                        _inspection: {
                            type: "object",
                            properties: {
                                identity_params: {
                                    type: "object",
                                    allOf: [{
                                        $ref: "#/$defs/rawEmailStatus"
                                    }, {
                                        $ref: "#/$defs/hashedEmailStatus"
                                    }]
                                }
                            }
                        }
                    }
                },
                $defs: {
                    validEmailFlag: {
                        type: "array",
                        not: {
                            contains: {
                                type: "string",
                                enum: ["unknown_invalid"]
                            }
                        }
                    },
                    rawEmailStatus: {
                        type: "object",
                        properties: {
                            email_is_hashed: {
                                $ref: "#/$defs/validEmailFlag"
                            }
                        }
                    },
                    hashedEmailStatus: {
                        properties: {
                            sha256_email: {
                                $ref: "#/$defs/validEmailFlag"
                            }
                        }
                    }
                }
            }
              , b = {
                type: "object",
                properties: {
                    email_is_hashed: {
                        $ref: "#/$defs/validEmailFlag"
                    }
                }
            }
              , O = {
                type: "array",
                not: {
                    contains: {
                        type: "string",
                        enum: ["unknown_invalid"]
                    }
                }
            };
            function M(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return M.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: b.type,
                        parentSchema: b,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.email_is_hashed) {
                    let r = e.email_is_hashed;
                    if (!Array.isArray(r))
                        return M.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validEmailFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: O.type,
                            parentSchema: O,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("unknown_invalid" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return M.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validEmailFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: O.not,
                            parentSchema: O,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return M.errors = n,
                0 === i
            }
            function S(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_email) {
                    let r = e.sha256_email;
                    if (!Array.isArray(r))
                        return S.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validEmailFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: O.type,
                            parentSchema: O,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("unknown_invalid" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return S.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validEmailFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: O.not,
                            parentSchema: O,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return S.errors = n,
                0 === i
            }
            function D(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return D.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: T.type,
                        parentSchema: T,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e))
                    if (void 0 === e._inspection && 1 || void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else {
                        if (void 0 !== e._inspection) {
                            let t = e._inspection
                              , r = i;
                            if (!(t && "object" == typeof t && !Array.isArray(t))) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var c = r === i
                        } else
                            var c = !0;
                        if (c)
                            if (void 0 !== e.event) {
                                let t = e.event
                                  , r = i;
                                if ("string" != typeof t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                let a = i
                                  , s = i;
                                if ("EnrichAM" !== t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                if (s === i) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                } else
                                    i = a,
                                    null !== n && (a ? n.length = a : n = null);
                                var c = r === i
                            } else
                                var c = !0
                    }
                var h = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                h) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e._inspection) {
                        let r = e._inspection
                          , a = i;
                        if (i === a) {
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return D.errors = [{
                                    instancePath: t + "/_inspection",
                                    schemaPath: "#/then/properties/_inspection/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: T.then.properties._inspection.type,
                                    parentSchema: T.then.properties._inspection,
                                    data: r
                                }],
                                !1;
                            else if (void 0 !== r.identity_params) {
                                let e = r.identity_params;
                                if (!(e && "object" == typeof e && !Array.isArray(e)))
                                    return D.errors = [{
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: T.then.properties._inspection.properties.identity_params.type,
                                        parentSchema: T.then.properties._inspection.properties.identity_params,
                                        data: e
                                    }],
                                    !1;
                                let a = i;
                                M(e, {
                                    instancePath: t + "/_inspection/identity_params",
                                    parentData: r,
                                    parentDataProperty: "identity_params",
                                    rootData: s
                                }) || (i = (n = null === n ? M.errors : n.concat(M.errors)).length);
                                var u = a === i;
                                if (u) {
                                    let a = i;
                                    S(e, {
                                        instancePath: t + "/_inspection/identity_params",
                                        parentData: r,
                                        parentDataProperty: "identity_params",
                                        rootData: s
                                    }) || (i = (n = null === n ? S.errors : n.concat(S.errors)).length);
                                    var u = a === i
                                }
                            }
                        }
                    }
                    var h = r === i;
                    p = h
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: T.if,
                        parentSchema: T,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    D.errors = n,
                    !1
                }
                return D.errors = n,
                0 === i
            }
            t.INVALID_EMAIL_INFORMATION = k;
            let j = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_EMAIL_INFORMATION",
                title: "INVALID_EMAIL_INFORMATION issue",
                type: "object",
                if: {
                    properties: {
                        _inspection: {
                            type: "object"
                        },
                        event: {
                            type: "string",
                            not: {
                                enum: ["EnrichAM"]
                            }
                        }
                    },
                    required: ["_inspection", "event"]
                },
                then: {
                    properties: {
                        _inspection: {
                            type: "object",
                            properties: {
                                identity_params: {
                                    type: "object",
                                    allOf: [{
                                        $ref: "#/$defs/rawEmailStatus"
                                    }, {
                                        $ref: "#/$defs/hashedEmailStatus"
                                    }]
                                }
                            }
                        }
                    }
                },
                $defs: {
                    validEmailFlag: {
                        type: "array",
                        not: {
                            contains: {
                                type: "string",
                                enum: ["filter_events"]
                            }
                        }
                    },
                    rawEmailStatus: {
                        type: "object",
                        properties: {
                            email_is_hashed: {
                                $ref: "#/$defs/validEmailFlag"
                            }
                        }
                    },
                    hashedEmailStatus: {
                        properties: {
                            sha256_email: {
                                $ref: "#/$defs/validEmailFlag"
                            }
                        }
                    }
                }
            }
              , R = {
                type: "object",
                properties: {
                    email_is_hashed: {
                        $ref: "#/$defs/validEmailFlag"
                    }
                }
            }
              , w = {
                type: "array",
                not: {
                    contains: {
                        type: "string",
                        enum: ["filter_events"]
                    }
                }
            };
            function L(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return L.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: R.type,
                        parentSchema: R,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.email_is_hashed) {
                    let r = e.email_is_hashed;
                    if (!Array.isArray(r))
                        return L.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validEmailFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: w.type,
                            parentSchema: w,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("filter_events" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return L.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validEmailFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: w.not,
                            parentSchema: w,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return L.errors = n,
                0 === i
            }
            function C(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_email) {
                    let r = e.sha256_email;
                    if (!Array.isArray(r))
                        return C.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validEmailFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: w.type,
                            parentSchema: w,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("filter_events" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return C.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validEmailFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: w.not,
                            parentSchema: w,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return C.errors = n,
                0 === i
            }
            function k(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return k.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: j.type,
                        parentSchema: j,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e))
                    if (void 0 === e._inspection && 1 || void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else {
                        if (void 0 !== e._inspection) {
                            let t = e._inspection
                              , r = i;
                            if (!(t && "object" == typeof t && !Array.isArray(t))) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var c = r === i
                        } else
                            var c = !0;
                        if (c)
                            if (void 0 !== e.event) {
                                let t = e.event
                                  , r = i;
                                if ("string" != typeof t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                let a = i
                                  , s = i;
                                if ("EnrichAM" !== t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                if (s === i) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                } else
                                    i = a,
                                    null !== n && (a ? n.length = a : n = null);
                                var c = r === i
                            } else
                                var c = !0
                    }
                var h = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                h) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e._inspection) {
                        let r = e._inspection
                          , a = i;
                        if (i === a) {
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return k.errors = [{
                                    instancePath: t + "/_inspection",
                                    schemaPath: "#/then/properties/_inspection/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: j.then.properties._inspection.type,
                                    parentSchema: j.then.properties._inspection,
                                    data: r
                                }],
                                !1;
                            else if (void 0 !== r.identity_params) {
                                let e = r.identity_params;
                                if (!(e && "object" == typeof e && !Array.isArray(e)))
                                    return k.errors = [{
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: j.then.properties._inspection.properties.identity_params.type,
                                        parentSchema: j.then.properties._inspection.properties.identity_params,
                                        data: e
                                    }],
                                    !1;
                                let a = i;
                                L(e, {
                                    instancePath: t + "/_inspection/identity_params",
                                    parentData: r,
                                    parentDataProperty: "identity_params",
                                    rootData: s
                                }) || (i = (n = null === n ? L.errors : n.concat(L.errors)).length);
                                var u = a === i;
                                if (u) {
                                    let a = i;
                                    C(e, {
                                        instancePath: t + "/_inspection/identity_params",
                                        parentData: r,
                                        parentDataProperty: "identity_params",
                                        rootData: s
                                    }) || (i = (n = null === n ? C.errors : n.concat(C.errors)).length);
                                    var u = a === i
                                }
                            }
                        }
                    }
                    var h = r === i;
                    p = h
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: j.if,
                        parentSchema: j,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    k.errors = n,
                    !1
                }
                return k.errors = n,
                0 === i
            }
            t.INVALID_EVENT_PARAMETER_VALUE = F;
            let V = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_EVENT_PARAMETER_VALUE",
                title: "INVALID_EVENT_PARAMETER_VALUE issue",
                type: "object",
                properties: {
                    properties: {
                        type: "object",
                        properties: {
                            value: {
                                anyOf: [{
                                    type: "string",
                                    pattern: "^\\d+(\\.\\d+)?$"
                                }, {
                                    type: "string",
                                    pattern: "^\\d+$"
                                }, {
                                    type: "number"
                                }]
                            }
                        }
                    }
                }
            }
              , x = RegExp("^\\d+(\\.\\d+)?$", "u")
              , $ = RegExp("^\\d+$", "u");
            function F(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return F.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: V.type,
                        parentSchema: V,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.properties) {
                    let r = e.properties
                      , a = i;
                    if (i === a) {
                        if (!r || "object" != typeof r || Array.isArray(r))
                            return F.errors = [{
                                instancePath: t + "/properties",
                                schemaPath: "#/properties/properties/type",
                                keyword: "type",
                                params: {
                                    type: "object"
                                },
                                message: "must be object",
                                schema: V.properties.properties.type,
                                parentSchema: V.properties.properties,
                                data: r
                            }],
                            !1;
                        else if (void 0 !== r.value) {
                            let e = r.value
                              , a = i
                              , s = !1
                              , p = i;
                            if (i === p)
                                if ("string" == typeof e) {
                                    if (!x.test(e)) {
                                        let r = {
                                            instancePath: t + "/properties/value",
                                            schemaPath: "#/properties/properties/properties/value/anyOf/0/pattern",
                                            keyword: "pattern",
                                            params: {
                                                pattern: "^\\d+(\\.\\d+)?$"
                                            },
                                            message: 'must match pattern "^\\d+(\\.\\d+)?$"',
                                            schema: "^\\d+(\\.\\d+)?$",
                                            parentSchema: V.properties.properties.properties.value.anyOf[0],
                                            data: e
                                        };
                                        null === n ? n = [r] : n.push(r),
                                        i++
                                    }
                                } else {
                                    let r = {
                                        instancePath: t + "/properties/value",
                                        schemaPath: "#/properties/properties/properties/value/anyOf/0/type",
                                        keyword: "type",
                                        params: {
                                            type: "string"
                                        },
                                        message: "must be string",
                                        schema: V.properties.properties.properties.value.anyOf[0].type,
                                        parentSchema: V.properties.properties.properties.value.anyOf[0],
                                        data: e
                                    };
                                    null === n ? n = [r] : n.push(r),
                                    i++
                                }
                            var o = p === i;
                            if (!(s = s || o)) {
                                let r = i;
                                if (i === r)
                                    if ("string" == typeof e) {
                                        if (!$.test(e)) {
                                            let r = {
                                                instancePath: t + "/properties/value",
                                                schemaPath: "#/properties/properties/properties/value/anyOf/1/pattern",
                                                keyword: "pattern",
                                                params: {
                                                    pattern: "^\\d+$"
                                                },
                                                message: 'must match pattern "^\\d+$"',
                                                schema: "^\\d+$",
                                                parentSchema: V.properties.properties.properties.value.anyOf[1],
                                                data: e
                                            };
                                            null === n ? n = [r] : n.push(r),
                                            i++
                                        }
                                    } else {
                                        let r = {
                                            instancePath: t + "/properties/value",
                                            schemaPath: "#/properties/properties/properties/value/anyOf/1/type",
                                            keyword: "type",
                                            params: {
                                                type: "string"
                                            },
                                            message: "must be string",
                                            schema: V.properties.properties.properties.value.anyOf[1].type,
                                            parentSchema: V.properties.properties.properties.value.anyOf[1],
                                            data: e
                                        };
                                        null === n ? n = [r] : n.push(r),
                                        i++
                                    }
                                var o = r === i;
                                if (!(s = s || o)) {
                                    let r = i;
                                    if ("number" != typeof e) {
                                        let r = {
                                            instancePath: t + "/properties/value",
                                            schemaPath: "#/properties/properties/properties/value/anyOf/2/type",
                                            keyword: "type",
                                            params: {
                                                type: "number"
                                            },
                                            message: "must be number",
                                            schema: V.properties.properties.properties.value.anyOf[2].type,
                                            parentSchema: V.properties.properties.properties.value.anyOf[2],
                                            data: e
                                        };
                                        null === n ? n = [r] : n.push(r),
                                        i++
                                    }
                                    var o = r === i;
                                    s = s || o
                                }
                            }
                            if (s)
                                i = a,
                                null !== n && (a ? n.length = a : n = null);
                            else {
                                let r = {
                                    instancePath: t + "/properties/value",
                                    schemaPath: "#/properties/properties/properties/value/anyOf",
                                    keyword: "anyOf",
                                    params: {},
                                    message: "must match a schema in anyOf",
                                    schema: V.properties.properties.properties.value.anyOf,
                                    parentSchema: V.properties.properties.properties.value,
                                    data: e
                                };
                                return null === n ? n = [r] : n.push(r),
                                i++,
                                F.errors = n,
                                !1
                            }
                        }
                    }
                }
                return F.errors = n,
                0 === i
            }
            t.INVALID_PHONE_NUMBER_FORMAT = q;
            let U = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_PHONE_NUMBER_FORMAT",
                title: "INVALID_PHONE_NUMBER_FORMAT issue",
                type: "object",
                if: {
                    properties: {
                        _inspection: {
                            type: "object"
                        },
                        event: {
                            type: "string",
                            not: {
                                enum: ["EnrichAM"]
                            }
                        }
                    },
                    required: ["_inspection", "event"]
                },
                then: {
                    properties: {
                        _inspection: {
                            type: "object",
                            properties: {
                                identity_params: {
                                    type: "object",
                                    allOf: [{
                                        $ref: "#/$defs/rawPhoneStatus"
                                    }, {
                                        $ref: "#/$defs/hashedPhoneStatus"
                                    }]
                                }
                            }
                        }
                    }
                },
                $defs: {
                    validPhoneFlag: {
                        type: "array",
                        not: {
                            contains: {
                                type: "string",
                                enum: ["unknown_invalid"]
                            }
                        }
                    },
                    rawPhoneStatus: {
                        type: "object",
                        properties: {
                            phone_is_hashed: {
                                $ref: "#/$defs/validPhoneFlag"
                            }
                        }
                    },
                    hashedPhoneStatus: {
                        properties: {
                            sha256_phone: {
                                $ref: "#/$defs/validPhoneFlag"
                            }
                        }
                    }
                }
            }
              , H = {
                type: "object",
                properties: {
                    phone_is_hashed: {
                        $ref: "#/$defs/validPhoneFlag"
                    }
                }
            }
              , G = {
                type: "array",
                not: {
                    contains: {
                        type: "string",
                        enum: ["unknown_invalid"]
                    }
                }
            };
            function Y(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return Y.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: H.type,
                        parentSchema: H,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.phone_is_hashed) {
                    let r = e.phone_is_hashed;
                    if (!Array.isArray(r))
                        return Y.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validPhoneFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: G.type,
                            parentSchema: G,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("unknown_invalid" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return Y.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validPhoneFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: G.not,
                            parentSchema: G,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return Y.errors = n,
                0 === i
            }
            function B(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_phone) {
                    let r = e.sha256_phone;
                    if (!Array.isArray(r))
                        return B.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validPhoneFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: G.type,
                            parentSchema: G,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("unknown_invalid" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return B.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validPhoneFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: G.not,
                            parentSchema: G,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return B.errors = n,
                0 === i
            }
            function q(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return q.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: U.type,
                        parentSchema: U,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e))
                    if (void 0 === e._inspection && 1 || void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else {
                        if (void 0 !== e._inspection) {
                            let t = e._inspection
                              , r = i;
                            if (!(t && "object" == typeof t && !Array.isArray(t))) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var c = r === i
                        } else
                            var c = !0;
                        if (c)
                            if (void 0 !== e.event) {
                                let t = e.event
                                  , r = i;
                                if ("string" != typeof t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                let a = i
                                  , s = i;
                                if ("EnrichAM" !== t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                if (s === i) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                } else
                                    i = a,
                                    null !== n && (a ? n.length = a : n = null);
                                var c = r === i
                            } else
                                var c = !0
                    }
                var h = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                h) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e._inspection) {
                        let r = e._inspection
                          , a = i;
                        if (i === a) {
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return q.errors = [{
                                    instancePath: t + "/_inspection",
                                    schemaPath: "#/then/properties/_inspection/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: U.then.properties._inspection.type,
                                    parentSchema: U.then.properties._inspection,
                                    data: r
                                }],
                                !1;
                            else if (void 0 !== r.identity_params) {
                                let e = r.identity_params;
                                if (!(e && "object" == typeof e && !Array.isArray(e)))
                                    return q.errors = [{
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: U.then.properties._inspection.properties.identity_params.type,
                                        parentSchema: U.then.properties._inspection.properties.identity_params,
                                        data: e
                                    }],
                                    !1;
                                let a = i;
                                Y(e, {
                                    instancePath: t + "/_inspection/identity_params",
                                    parentData: r,
                                    parentDataProperty: "identity_params",
                                    rootData: s
                                }) || (i = (n = null === n ? Y.errors : n.concat(Y.errors)).length);
                                var u = a === i;
                                if (u) {
                                    let a = i;
                                    B(e, {
                                        instancePath: t + "/_inspection/identity_params",
                                        parentData: r,
                                        parentDataProperty: "identity_params",
                                        rootData: s
                                    }) || (i = (n = null === n ? B.errors : n.concat(B.errors)).length);
                                    var u = a === i
                                }
                            }
                        }
                    }
                    var h = r === i;
                    p = h
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: U.if,
                        parentSchema: U,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    q.errors = n,
                    !1
                }
                return q.errors = n,
                0 === i
            }
            t.INVALID_PHONE_NUMBER_INFORMATION = J;
            let K = {
                $schema: "/draft-07/schema#",
                $id: "INVALID_PHONE_NUMBER_INFORMATION",
                title: "INVALID_PHONE_NUMBER_INFORMATION issue",
                type: "object",
                if: {
                    properties: {
                        _inspection: {
                            type: "object"
                        },
                        event: {
                            type: "string",
                            not: {
                                enum: ["EnrichAM"]
                            }
                        }
                    },
                    required: ["_inspection", "event"]
                },
                then: {
                    properties: {
                        _inspection: {
                            type: "object",
                            properties: {
                                identity_params: {
                                    type: "object",
                                    allOf: [{
                                        $ref: "#/$defs/rawPhoneStatus"
                                    }, {
                                        $ref: "#/$defs/hashedPhoneStatus"
                                    }]
                                }
                            }
                        }
                    }
                },
                $defs: {
                    validPhoneFlag: {
                        type: "array",
                        not: {
                            contains: {
                                type: "string",
                                enum: ["filter_events"]
                            }
                        }
                    },
                    rawPhoneStatus: {
                        type: "object",
                        properties: {
                            phone_is_hashed: {
                                $ref: "#/$defs/validPhoneFlag"
                            }
                        }
                    },
                    hashedPhoneStatus: {
                        properties: {
                            sha256_phone: {
                                $ref: "#/$defs/validPhoneFlag"
                            }
                        }
                    }
                }
            }
              , Z = {
                type: "object",
                properties: {
                    phone_is_hashed: {
                        $ref: "#/$defs/validPhoneFlag"
                    }
                }
            }
              , z = {
                type: "array",
                not: {
                    contains: {
                        type: "string",
                        enum: ["filter_events"]
                    }
                }
            };
            function W(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return W.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: Z.type,
                        parentSchema: Z,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.phone_is_hashed) {
                    let r = e.phone_is_hashed;
                    if (!Array.isArray(r))
                        return W.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validPhoneFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: z.type,
                            parentSchema: z,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("filter_events" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return W.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validPhoneFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: z.not,
                            parentSchema: z,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return W.errors = n,
                0 === i
            }
            function Q(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_phone) {
                    let r = e.sha256_phone;
                    if (!Array.isArray(r))
                        return Q.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validPhoneFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: z.type,
                            parentSchema: z,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("filter_events" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return Q.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validPhoneFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: z.not,
                            parentSchema: z,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return Q.errors = n,
                0 === i
            }
            function J(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return J.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: K.type,
                        parentSchema: K,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e))
                    if (void 0 === e._inspection && 1 || void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else {
                        if (void 0 !== e._inspection) {
                            let t = e._inspection
                              , r = i;
                            if (!(t && "object" == typeof t && !Array.isArray(t))) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var c = r === i
                        } else
                            var c = !0;
                        if (c)
                            if (void 0 !== e.event) {
                                let t = e.event
                                  , r = i;
                                if ("string" != typeof t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                let a = i
                                  , s = i;
                                if ("EnrichAM" !== t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                if (s === i) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                } else
                                    i = a,
                                    null !== n && (a ? n.length = a : n = null);
                                var c = r === i
                            } else
                                var c = !0
                    }
                var h = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                h) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e._inspection) {
                        let r = e._inspection
                          , a = i;
                        if (i === a) {
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return J.errors = [{
                                    instancePath: t + "/_inspection",
                                    schemaPath: "#/then/properties/_inspection/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: K.then.properties._inspection.type,
                                    parentSchema: K.then.properties._inspection,
                                    data: r
                                }],
                                !1;
                            else if (void 0 !== r.identity_params) {
                                let e = r.identity_params;
                                if (!(e && "object" == typeof e && !Array.isArray(e)))
                                    return J.errors = [{
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: K.then.properties._inspection.properties.identity_params.type,
                                        parentSchema: K.then.properties._inspection.properties.identity_params,
                                        data: e
                                    }],
                                    !1;
                                let a = i;
                                W(e, {
                                    instancePath: t + "/_inspection/identity_params",
                                    parentData: r,
                                    parentDataProperty: "identity_params",
                                    rootData: s
                                }) || (i = (n = null === n ? W.errors : n.concat(W.errors)).length);
                                var u = a === i;
                                if (u) {
                                    let a = i;
                                    Q(e, {
                                        instancePath: t + "/_inspection/identity_params",
                                        parentData: r,
                                        parentDataProperty: "identity_params",
                                        rootData: s
                                    }) || (i = (n = null === n ? Q.errors : n.concat(Q.errors)).length);
                                    var u = a === i
                                }
                            }
                        }
                    }
                    var h = r === i;
                    p = h
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: K.if,
                        parentSchema: K,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    J.errors = n,
                    !1
                }
                return J.errors = n,
                0 === i
            }
            t.LONG_EVENT_TYPE_NAME = ee;
            let X = {
                $schema: "/draft-07/schema#",
                $id: "LONG_EVENT_TYPE_NAME",
                title: "LONG_EVENT_TYPE_NAME issue",
                type: "object",
                if: {
                    properties: {
                        event: {
                            not: {
                                pattern: "^\\s*$"
                            }
                        }
                    },
                    required: ["event"]
                },
                then: {
                    properties: {
                        event: {
                            type: "string",
                            maxLength: 50
                        }
                    }
                }
            };
            function ee(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: n=e}={}) {
                let i = null
                  , o = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return ee.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: X.type,
                        parentSchema: X,
                        data: e
                    }],
                    !1;
                let p = o
                  , c = !0
                  , h = o;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === i ? i = [e] : i.push(e),
                        o++
                    } else if (void 0 !== e.event) {
                        let t = e.event
                          , r = o
                          , a = o;
                        if ("string" == typeof t && !s.test(t)) {
                            let e = {};
                            null === i ? i = [e] : i.push(e),
                            o++
                        }
                        if (a === o) {
                            let e = {};
                            null === i ? i = [e] : i.push(e),
                            o++
                        } else
                            o = r,
                            null !== i && (r ? i.length = r : i = null)
                    }
                }
                var u = h === o;
                if (o = p,
                null !== i && (p ? i.length = p : i = null),
                u) {
                    let r = o;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.event) {
                        let r = e.event
                          , a = o;
                        if (o === a) {
                            if ("string" != typeof r)
                                return ee.errors = [{
                                    instancePath: t + "/event",
                                    schemaPath: "#/then/properties/event/type",
                                    keyword: "type",
                                    params: {
                                        type: "string"
                                    },
                                    message: "must be string",
                                    schema: X.then.properties.event.type,
                                    parentSchema: X.then.properties.event,
                                    data: r
                                }],
                                !1;
                            else if (l(r) > 50)
                                return ee.errors = [{
                                    instancePath: t + "/event",
                                    schemaPath: "#/then/properties/event/maxLength",
                                    keyword: "maxLength",
                                    params: {
                                        limit: 50
                                    },
                                    message: "must NOT have more than 50 characters",
                                    schema: 50,
                                    parentSchema: X.then.properties.event,
                                    data: r
                                }],
                                !1
                        }
                    }
                    var u = r === o;
                    c = u
                }
                if (!c) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: X.if,
                        parentSchema: X,
                        data: e
                    };
                    return null === i ? i = [r] : i.push(r),
                    o++,
                    ee.errors = i,
                    !1
                }
                return ee.errors = i,
                0 === o
            }
            t.MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT = ea;
            let et = {
                $schema: "/draft-07/schema#",
                $id: "MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT",
                title: "MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT issue",
                type: "object",
                if: {
                    properties: {
                        event: {
                            not: {
                                pattern: "^\\s*$"
                            }
                        }
                    },
                    required: ["event"]
                },
                then: {
                    properties: {
                        event: {
                            pattern: "^[a-zA-Z\\d]([a-zA-Z_\\-\\d ]{0,}[a-zA-Z_\\-\\d])?$"
                        }
                    }
                }
            }
              , er = RegExp("^[a-zA-Z\\d]([a-zA-Z_\\-\\d ]{0,}[a-zA-Z_\\-\\d])?$", "u");
            function ea(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: n=e}={}) {
                let i = null
                  , o = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return ea.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: et.type,
                        parentSchema: et,
                        data: e
                    }],
                    !1;
                let p = o
                  , l = !0
                  , c = o;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === i ? i = [e] : i.push(e),
                        o++
                    } else if (void 0 !== e.event) {
                        let t = e.event
                          , r = o
                          , a = o;
                        if ("string" == typeof t && !s.test(t)) {
                            let e = {};
                            null === i ? i = [e] : i.push(e),
                            o++
                        }
                        if (a === o) {
                            let e = {};
                            null === i ? i = [e] : i.push(e),
                            o++
                        } else
                            o = r,
                            null !== i && (r ? i.length = r : i = null)
                    }
                }
                var h = c === o;
                if (o = p,
                null !== i && (p ? i.length = p : i = null),
                h) {
                    let r = o;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.event) {
                        let r = e.event;
                        if ("string" == typeof r && !er.test(r))
                            return ea.errors = [{
                                instancePath: t + "/event",
                                schemaPath: "#/then/properties/event/pattern",
                                keyword: "pattern",
                                params: {
                                    pattern: "^[a-zA-Z\\d]([a-zA-Z_\\-\\d ]{0,}[a-zA-Z_\\-\\d])?$"
                                },
                                message: 'must match pattern "^[a-zA-Z\\d]([a-zA-Z_\\-\\d ]{0,}[a-zA-Z_\\-\\d])?$"',
                                schema: "^[a-zA-Z\\d]([a-zA-Z_\\-\\d ]{0,}[a-zA-Z_\\-\\d])?$",
                                parentSchema: et.then.properties.event,
                                data: r
                            }],
                            !1
                    }
                    var h = r === o;
                    l = h
                }
                if (!l) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: et.if,
                        parentSchema: et,
                        data: e
                    };
                    return null === i ? i = [r] : i.push(r),
                    o++,
                    ea.errors = i,
                    !1
                }
                return ea.errors = i,
                0 === o
            }
            t.MISSING_CONTENT_ID = eo;
            let es = {
                $schema: "/draft-07/schema#",
                $id: "MISSING_CONTENT_ID",
                title: "MISSING_CONTENT_ID issue",
                type: "object",
                if: {
                    properties: {
                        event: {
                            $ref: "#/$defs/ecomEvent"
                        }
                    },
                    required: ["event"]
                },
                then: {
                    properties: {
                        properties: {
                            type: "object",
                            anyOf: [{
                                $ref: "#/$defs/singleProduct"
                            }, {
                                $ref: "#/$defs/multiProducts"
                            }]
                        }
                    }
                },
                $defs: {
                    ecomEvent: {
                        type: "string",
                        enum: ["CompletePayment", "InitiateCheckout", "AddToCart", "PlaceAnOrder", "ViewContent", "AddToWishlist"]
                    },
                    singleProduct: {
                        type: "object",
                        anyOf: [{
                            required: ["content_id"]
                        }, {
                            required: ["content_ids"]
                        }],
                        allOf: [{
                            if: {
                                properties: {
                                    content_ids: {
                                        type: "array"
                                    }
                                }
                            },
                            then: {
                                properties: {
                                    content_ids: {
                                        minItems: 1
                                    }
                                }
                            }
                        }]
                    },
                    multiProducts: {
                        type: "object",
                        properties: {
                            contents: {
                                type: "array",
                                minItems: 1,
                                items: {
                                    required: ["content_id"]
                                }
                            }
                        },
                        required: ["contents"]
                    }
                }
            }
              , en = {
                type: "object",
                anyOf: [{
                    required: ["content_id"]
                }, {
                    required: ["content_ids"]
                }],
                allOf: [{
                    if: {
                        properties: {
                            content_ids: {
                                type: "array"
                            }
                        }
                    },
                    then: {
                        properties: {
                            content_ids: {
                                minItems: 1
                            }
                        }
                    }
                }]
            }
              , ei = {
                type: "object",
                properties: {
                    contents: {
                        type: "array",
                        minItems: 1,
                        items: {
                            required: ["content_id"]
                        }
                    }
                },
                required: ["contents"]
            };
            function eo(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return eo.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: es.type,
                        parentSchema: es,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else if (void 0 !== e.event) {
                        let t = e.event;
                        if ("string" != typeof t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                        if ("CompletePayment" !== t && "InitiateCheckout" !== t && "AddToCart" !== t && "PlaceAnOrder" !== t && "ViewContent" !== t && "AddToWishlist" !== t) {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                }
                var c = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                c) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                        let r = e.properties;
                        if (!(r && "object" == typeof r && !Array.isArray(r)))
                            return eo.errors = [{
                                instancePath: t + "/properties",
                                schemaPath: "#/then/properties/properties/type",
                                keyword: "type",
                                params: {
                                    type: "object"
                                },
                                message: "must be object",
                                schema: es.then.properties.properties.type,
                                parentSchema: es.then.properties.properties,
                                data: r
                            }],
                            !1;
                        let a = i
                          , s = !1
                          , o = i;
                        if (!(r && "object" == typeof r && !Array.isArray(r))) {
                            let e = {
                                instancePath: t + "/properties",
                                schemaPath: "#/$defs/singleProduct/type",
                                keyword: "type",
                                params: {
                                    type: "object"
                                },
                                message: "must be object",
                                schema: en.type,
                                parentSchema: en,
                                data: r
                            };
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                        let p = i
                          , l = !1
                          , c = i;
                        if (r && "object" == typeof r && !Array.isArray(r)) {
                            let e;
                            if (void 0 === r.content_id && (e = "content_id")) {
                                let a = {
                                    instancePath: t + "/properties",
                                    schemaPath: "#/$defs/singleProduct/anyOf/0/required",
                                    keyword: "required",
                                    params: {
                                        missingProperty: e
                                    },
                                    message: "must have required property '" + e + "'",
                                    schema: en.anyOf[0].required,
                                    parentSchema: en.anyOf[0],
                                    data: r
                                };
                                null === n ? n = [a] : n.push(a),
                                i++
                            }
                        }
                        var h = c === i;
                        if (!(l = l || h)) {
                            let e = i;
                            if (r && "object" == typeof r && !Array.isArray(r)) {
                                let e;
                                if (void 0 === r.content_ids && (e = "content_ids")) {
                                    let a = {
                                        instancePath: t + "/properties",
                                        schemaPath: "#/$defs/singleProduct/anyOf/1/required",
                                        keyword: "required",
                                        params: {
                                            missingProperty: e
                                        },
                                        message: "must have required property '" + e + "'",
                                        schema: en.anyOf[1].required,
                                        parentSchema: en.anyOf[1],
                                        data: r
                                    };
                                    null === n ? n = [a] : n.push(a),
                                    i++
                                }
                            }
                            var h = e === i;
                            l = l || h
                        }
                        if (l) {
                            i = p,
                            null !== n && (p ? n.length = p : n = null);
                            let e = i
                              , a = !0
                              , s = i;
                            if (r && "object" == typeof r && !Array.isArray(r) && void 0 !== r.content_ids && !Array.isArray(r.content_ids)) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var u = s === i;
                            if (i = e,
                            null !== n && (e ? n.length = e : n = null),
                            u) {
                                let e = i;
                                if (r && "object" == typeof r && !Array.isArray(r) && void 0 !== r.content_ids) {
                                    let e = r.content_ids;
                                    if (Array.isArray(e) && e.length < 1) {
                                        let r = {
                                            instancePath: t + "/properties/content_ids",
                                            schemaPath: "#/$defs/singleProduct/allOf/0/then/properties/content_ids/minItems",
                                            keyword: "minItems",
                                            params: {
                                                limit: 1
                                            },
                                            message: "must NOT have fewer than 1 items",
                                            schema: 1,
                                            parentSchema: en.allOf[0].then.properties.content_ids,
                                            data: e
                                        };
                                        null === n ? n = [r] : n.push(r),
                                        i++
                                    }
                                }
                                var u = e === i;
                                a = u
                            }
                            if (!a) {
                                let e = {
                                    instancePath: t + "/properties",
                                    schemaPath: "#/$defs/singleProduct/allOf/0/if",
                                    keyword: "if",
                                    params: {
                                        failingKeyword: "then"
                                    },
                                    message: 'must match "then" schema',
                                    schema: en.allOf[0].if,
                                    parentSchema: en.allOf[0],
                                    data: r
                                };
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                        } else {
                            let e = {
                                instancePath: t + "/properties",
                                schemaPath: "#/$defs/singleProduct/anyOf",
                                keyword: "anyOf",
                                params: {},
                                message: "must match a schema in anyOf",
                                schema: en.anyOf,
                                parentSchema: en,
                                data: r
                            };
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                        var d = o === i;
                        if (!(s = s || d)) {
                            let e = i
                              , a = i;
                            if (i === a)
                                if (r && "object" == typeof r && !Array.isArray(r)) {
                                    let e;
                                    if (void 0 === r.contents && (e = "contents")) {
                                        let a = {
                                            instancePath: t + "/properties",
                                            schemaPath: "#/$defs/multiProducts/required",
                                            keyword: "required",
                                            params: {
                                                missingProperty: e
                                            },
                                            message: "must have required property '" + e + "'",
                                            schema: ei.required,
                                            parentSchema: ei,
                                            data: r
                                        };
                                        null === n ? n = [a] : n.push(a),
                                        i++
                                    } else if (void 0 !== r.contents) {
                                        let e = r.contents
                                          , a = i;
                                        if (i === a)
                                            if (Array.isArray(e))
                                                if (e.length < 1) {
                                                    let r = {
                                                        instancePath: t + "/properties/contents",
                                                        schemaPath: "#/$defs/multiProducts/properties/contents/minItems",
                                                        keyword: "minItems",
                                                        params: {
                                                            limit: 1
                                                        },
                                                        message: "must NOT have fewer than 1 items",
                                                        schema: 1,
                                                        parentSchema: ei.properties.contents,
                                                        data: e
                                                    };
                                                    null === n ? n = [r] : n.push(r),
                                                    i++
                                                } else {
                                                    var m = !0;
                                                    let r = e.length;
                                                    for (let a = 0; a < r; a++) {
                                                        let r = e[a]
                                                          , s = i;
                                                        if (r && "object" == typeof r && !Array.isArray(r)) {
                                                            let e;
                                                            if (void 0 === r.content_id && (e = "content_id")) {
                                                                let s = {
                                                                    instancePath: t + "/properties/contents/" + a,
                                                                    schemaPath: "#/$defs/multiProducts/properties/contents/items/required",
                                                                    keyword: "required",
                                                                    params: {
                                                                        missingProperty: e
                                                                    },
                                                                    message: "must have required property '" + e + "'",
                                                                    schema: ei.properties.contents.items.required,
                                                                    parentSchema: ei.properties.contents.items,
                                                                    data: r
                                                                };
                                                                null === n ? n = [s] : n.push(s),
                                                                i++
                                                            }
                                                        }
                                                        var m = s === i;
                                                        if (!m)
                                                            break
                                                    }
                                                }
                                            else {
                                                let r = {
                                                    instancePath: t + "/properties/contents",
                                                    schemaPath: "#/$defs/multiProducts/properties/contents/type",
                                                    keyword: "type",
                                                    params: {
                                                        type: "array"
                                                    },
                                                    message: "must be array",
                                                    schema: ei.properties.contents.type,
                                                    parentSchema: ei.properties.contents,
                                                    data: e
                                                };
                                                null === n ? n = [r] : n.push(r),
                                                i++
                                            }
                                    }
                                } else {
                                    let e = {
                                        instancePath: t + "/properties",
                                        schemaPath: "#/$defs/multiProducts/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: ei.type,
                                        parentSchema: ei,
                                        data: r
                                    };
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                            var d = e === i;
                            s = s || d
                        }
                        if (s)
                            i = a,
                            null !== n && (a ? n.length = a : n = null);
                        else {
                            let e = {
                                instancePath: t + "/properties",
                                schemaPath: "#/then/properties/properties/anyOf",
                                keyword: "anyOf",
                                params: {},
                                message: "must match a schema in anyOf",
                                schema: es.then.properties.properties.anyOf,
                                parentSchema: es.then.properties.properties,
                                data: r
                            };
                            return null === n ? n = [e] : n.push(e),
                            i++,
                            eo.errors = n,
                            !1
                        }
                    }
                    var c = r === i;
                    p = c
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: es.if,
                        parentSchema: es,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    eo.errors = n,
                    !1
                }
                return eo.errors = n,
                0 === i
            }
            t.MISSING_CURRENCY_PARAMETER = el;
            let ep = {
                $schema: "/draft-07/schema#",
                $id: "MISSING_CURRENCY_PARAMETER",
                title: "MISSING_CURRENCY_PARAMETER issue",
                allOf: [{
                    type: "object",
                    if: {
                        properties: {
                            event: {
                                const: "CompletePayment"
                            }
                        },
                        required: ["event"]
                    },
                    then: {
                        properties: {
                            properties: {
                                type: "object",
                                required: ["currency"]
                            }
                        }
                    }
                }, {
                    type: "object",
                    if: {
                        properties: {
                            event: {
                                not: {
                                    const: "CompletePayment"
                                }
                            },
                            properties: {
                                type: "object",
                                required: ["value"]
                            }
                        }
                    },
                    then: {
                        properties: {
                            properties: {
                                type: "object",
                                required: ["currency"]
                            }
                        }
                    }
                }]
            };
            function el(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return el.errors = [{
                        instancePath: t,
                        schemaPath: "#/allOf/0/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: ep.allOf[0].type,
                        parentSchema: ep.allOf[0],
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else if (void 0 !== e.event && "CompletePayment" !== e.event) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    }
                }
                var c = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                c) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                        let r = e.properties
                          , a = i;
                        if (i === a)
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return el.errors = [{
                                    instancePath: t + "/properties",
                                    schemaPath: "#/allOf/0/then/properties/properties/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: ep.allOf[0].then.properties.properties.type,
                                    parentSchema: ep.allOf[0].then.properties.properties,
                                    data: r
                                }],
                                !1;
                            else {
                                let e;
                                if (void 0 === r.currency && (e = "currency"))
                                    return el.errors = [{
                                        instancePath: t + "/properties",
                                        schemaPath: "#/allOf/0/then/properties/properties/required",
                                        keyword: "required",
                                        params: {
                                            missingProperty: e
                                        },
                                        message: "must have required property '" + e + "'",
                                        schema: ep.allOf[0].then.properties.properties.required,
                                        parentSchema: ep.allOf[0].then.properties.properties,
                                        data: r
                                    }],
                                    !1
                            }
                    }
                    var c = r === i;
                    p = c
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/allOf/0/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: ep.allOf[0].if,
                        parentSchema: ep.allOf[0],
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    el.errors = n,
                    !1
                }
                var h = 0 === i;
                if (h) {
                    let r = i;
                    if (!(e && "object" == typeof e && !Array.isArray(e)))
                        return el.errors = [{
                            instancePath: t,
                            schemaPath: "#/allOf/1/type",
                            keyword: "type",
                            params: {
                                type: "object"
                            },
                            message: "must be object",
                            schema: ep.allOf[1].type,
                            parentSchema: ep.allOf[1],
                            data: e
                        }],
                        !1;
                    let a = i
                      , s = !0
                      , o = i;
                    if (e && "object" == typeof e && !Array.isArray(e)) {
                        if (void 0 !== e.event) {
                            let t = i
                              , r = i
                              , a = i;
                            if ("CompletePayment" !== e.event) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if (a === i) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            } else
                                i = r,
                                null !== n && (r ? n.length = r : n = null);
                            var u = t === i
                        } else
                            var u = !0;
                        if (u)
                            if (void 0 !== e.properties) {
                                let t = e.properties
                                  , r = i;
                                if (i === r)
                                    if (t && "object" == typeof t && !Array.isArray(t)) {
                                        if (void 0 === t.value && 1) {
                                            let e = {};
                                            null === n ? n = [e] : n.push(e),
                                            i++
                                        }
                                    } else {
                                        let e = {};
                                        null === n ? n = [e] : n.push(e),
                                        i++
                                    }
                                var u = r === i
                            } else
                                var u = !0
                    }
                    var d = o === i;
                    if (i = a,
                    null !== n && (a ? n.length = a : n = null),
                    d) {
                        let r = i;
                        if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                            let r = e.properties
                              , a = i;
                            if (i === a)
                                if (!r || "object" != typeof r || Array.isArray(r))
                                    return el.errors = [{
                                        instancePath: t + "/properties",
                                        schemaPath: "#/allOf/1/then/properties/properties/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: ep.allOf[1].then.properties.properties.type,
                                        parentSchema: ep.allOf[1].then.properties.properties,
                                        data: r
                                    }],
                                    !1;
                                else {
                                    let e;
                                    if (void 0 === r.currency && (e = "currency"))
                                        return el.errors = [{
                                            instancePath: t + "/properties",
                                            schemaPath: "#/allOf/1/then/properties/properties/required",
                                            keyword: "required",
                                            params: {
                                                missingProperty: e
                                            },
                                            message: "must have required property '" + e + "'",
                                            schema: ep.allOf[1].then.properties.properties.required,
                                            parentSchema: ep.allOf[1].then.properties.properties,
                                            data: r
                                        }],
                                        !1
                                }
                        }
                        var d = r === i;
                        s = d
                    }
                    if (!s) {
                        let r = {
                            instancePath: t,
                            schemaPath: "#/allOf/1/if",
                            keyword: "if",
                            params: {
                                failingKeyword: "then"
                            },
                            message: 'must match "then" schema',
                            schema: ep.allOf[1].if,
                            parentSchema: ep.allOf[1],
                            data: e
                        };
                        return null === n ? n = [r] : n.push(r),
                        i++,
                        el.errors = n,
                        !1
                    }
                    var h = r === i
                }
                return el.errors = n,
                0 === i
            }
            t.MISSING_EMAIL_AND_PHONE = eg;
            let ec = {
                $schema: "/draft-07/schema#",
                $id: "MISSING_EMAIL_AND_PHONE",
                title: "MISSING_EMAIL_AND_PHONE issue",
                type: "object",
                if: {
                    properties: {
                        _inspection: {
                            type: "object"
                        },
                        event: {
                            type: "string",
                            enum: ["CompletePayment"]
                        }
                    },
                    required: ["_inspection", "event"]
                },
                then: {
                    properties: {
                        _inspection: {
                            type: "object",
                            properties: {
                                identity_params: {
                                    type: "object",
                                    anyOf: [{
                                        $ref: "#/$defs/rawPhoneStatus"
                                    }, {
                                        $ref: "#/$defs/hashedPhoneStatus"
                                    }, {
                                        $ref: "#/$defs/rawEmailStatus"
                                    }, {
                                        $ref: "#/$defs/hashedEmailStatus"
                                    }]
                                }
                            }
                        }
                    }
                },
                $defs: {
                    validFlag: {
                        type: "array",
                        not: {
                            contains: {
                                type: "string",
                                enum: ["empty_value"]
                            }
                        }
                    },
                    rawPhoneStatus: {
                        type: "object",
                        properties: {
                            phone_is_hashed: {
                                $ref: "#/$defs/validFlag"
                            }
                        }
                    },
                    hashedPhoneStatus: {
                        properties: {
                            sha256_phone: {
                                $ref: "#/$defs/validFlag"
                            }
                        }
                    },
                    rawEmailStatus: {
                        type: "object",
                        properties: {
                            email_is_hashed: {
                                $ref: "#/$defs/validFlag"
                            }
                        }
                    },
                    hashedEmailStatus: {
                        properties: {
                            sha256_email: {
                                $ref: "#/$defs/validFlag"
                            }
                        }
                    }
                }
            }
              , eh = {
                type: "object",
                properties: {
                    phone_is_hashed: {
                        $ref: "#/$defs/validFlag"
                    }
                }
            }
              , eu = {
                type: "array",
                not: {
                    contains: {
                        type: "string",
                        enum: ["empty_value"]
                    }
                }
            };
            function ed(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return ed.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: eh.type,
                        parentSchema: eh,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.phone_is_hashed) {
                    let r = e.phone_is_hashed;
                    if (!Array.isArray(r))
                        return ed.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: eu.type,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("empty_value" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return ed.errors = [{
                            instancePath: t + "/phone_is_hashed",
                            schemaPath: "#/$defs/validFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: eu.not,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return ed.errors = n,
                0 === i
            }
            function em(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_phone) {
                    let r = e.sha256_phone;
                    if (!Array.isArray(r))
                        return em.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: eu.type,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("empty_value" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return em.errors = [{
                            instancePath: t + "/sha256_phone",
                            schemaPath: "#/$defs/validFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: eu.not,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return em.errors = n,
                0 === i
            }
            let ey = {
                type: "object",
                properties: {
                    email_is_hashed: {
                        $ref: "#/$defs/validFlag"
                    }
                }
            };
            function ef(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!e || "object" != typeof e || Array.isArray(e))
                    return ef.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: ey.type,
                        parentSchema: ey,
                        data: e
                    }],
                    !1;
                if (void 0 !== e.email_is_hashed) {
                    let r = e.email_is_hashed;
                    if (!Array.isArray(r))
                        return ef.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: eu.type,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("empty_value" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return ef.errors = [{
                            instancePath: t + "/email_is_hashed",
                            schemaPath: "#/$defs/validFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: eu.not,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return ef.errors = n,
                0 === i
            }
            function e_(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.sha256_email) {
                    let r = e.sha256_email;
                    if (!Array.isArray(r))
                        return e_.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validFlag/type",
                            keyword: "type",
                            params: {
                                type: "array"
                            },
                            message: "must be array",
                            schema: eu.type,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    let a = i
                      , s = i;
                    if (Array.isArray(r)) {
                        let e = i
                          , t = r.length;
                        for (let e = 0; e < t; e++) {
                            let t = r[e]
                              , a = i;
                            if ("string" != typeof t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if ("empty_value" !== t) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var o = a === i;
                            if (o)
                                break
                        }
                        if (o)
                            i = e,
                            null !== n && (e ? n.length = e : n = null);
                        else {
                            let e = {};
                            null === n ? n = [e] : n.push(e),
                            i++
                        }
                    }
                    if (s === i)
                        return e_.errors = [{
                            instancePath: t + "/sha256_email",
                            schemaPath: "#/$defs/validFlag/not",
                            keyword: "not",
                            params: {},
                            message: "must NOT be valid",
                            schema: eu.not,
                            parentSchema: eu,
                            data: r
                        }],
                        !1;
                    i = a,
                    null !== n && (a ? n.length = a : n = null)
                }
                return e_.errors = n,
                0 === i
            }
            function eg(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return eg.errors = [{
                        instancePath: t,
                        schemaPath: "#/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: ec.type,
                        parentSchema: ec,
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e))
                    if (void 0 === e._inspection && 1 || void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else {
                        if (void 0 !== e._inspection) {
                            let t = e._inspection
                              , r = i;
                            if (!(t && "object" == typeof t && !Array.isArray(t))) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            var c = r === i
                        } else
                            var c = !0;
                        if (c)
                            if (void 0 !== e.event) {
                                let t = e.event
                                  , r = i;
                                if ("string" != typeof t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                if ("CompletePayment" !== t) {
                                    let e = {};
                                    null === n ? n = [e] : n.push(e),
                                    i++
                                }
                                var c = r === i
                            } else
                                var c = !0
                    }
                var h = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                h) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e._inspection) {
                        let r = e._inspection
                          , a = i;
                        if (i === a) {
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return eg.errors = [{
                                    instancePath: t + "/_inspection",
                                    schemaPath: "#/then/properties/_inspection/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: ec.then.properties._inspection.type,
                                    parentSchema: ec.then.properties._inspection,
                                    data: r
                                }],
                                !1;
                            else if (void 0 !== r.identity_params) {
                                let e = r.identity_params;
                                if (!(e && "object" == typeof e && !Array.isArray(e)))
                                    return eg.errors = [{
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: ec.then.properties._inspection.properties.identity_params.type,
                                        parentSchema: ec.then.properties._inspection.properties.identity_params,
                                        data: e
                                    }],
                                    !1;
                                let a = i
                                  , o = !1
                                  , p = i;
                                ed(e, {
                                    instancePath: t + "/_inspection/identity_params",
                                    parentData: r,
                                    parentDataProperty: "identity_params",
                                    rootData: s
                                }) || (i = (n = null === n ? ed.errors : n.concat(ed.errors)).length);
                                var u = p === i;
                                if (!(o = o || u)) {
                                    let a = i;
                                    em(e, {
                                        instancePath: t + "/_inspection/identity_params",
                                        parentData: r,
                                        parentDataProperty: "identity_params",
                                        rootData: s
                                    }) || (i = (n = null === n ? em.errors : n.concat(em.errors)).length);
                                    var u = a === i;
                                    if (!(o = o || u)) {
                                        let a = i;
                                        ef(e, {
                                            instancePath: t + "/_inspection/identity_params",
                                            parentData: r,
                                            parentDataProperty: "identity_params",
                                            rootData: s
                                        }) || (i = (n = null === n ? ef.errors : n.concat(ef.errors)).length);
                                        var u = a === i;
                                        if (!(o = o || u)) {
                                            let a = i;
                                            e_(e, {
                                                instancePath: t + "/_inspection/identity_params",
                                                parentData: r,
                                                parentDataProperty: "identity_params",
                                                rootData: s
                                            }) || (i = (n = null === n ? e_.errors : n.concat(e_.errors)).length);
                                            var u = a === i;
                                            o = o || u
                                        }
                                    }
                                }
                                if (o)
                                    i = a,
                                    null !== n && (a ? n.length = a : n = null);
                                else {
                                    let r = {
                                        instancePath: t + "/_inspection/identity_params",
                                        schemaPath: "#/then/properties/_inspection/properties/identity_params/anyOf",
                                        keyword: "anyOf",
                                        params: {},
                                        message: "must match a schema in anyOf",
                                        schema: ec.then.properties._inspection.properties.identity_params.anyOf,
                                        parentSchema: ec.then.properties._inspection.properties.identity_params,
                                        data: e
                                    };
                                    return null === n ? n = [r] : n.push(r),
                                    i++,
                                    eg.errors = n,
                                    !1
                                }
                            }
                        }
                    }
                    var h = r === i;
                    p = h
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: ec.if,
                        parentSchema: ec,
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    eg.errors = n,
                    !1
                }
                return eg.errors = n,
                0 === i
            }
            t.MISSING_VALUE_PARAMETER = eE;
            let ev = {
                $schema: "/draft-07/schema#",
                $id: "MISSING_VALUE_PARAMETER",
                title: "MISSING_VALUE_PARAMETER issue",
                allOf: [{
                    type: "object",
                    if: {
                        properties: {
                            event: {
                                const: "CompletePayment"
                            }
                        },
                        required: ["event"]
                    },
                    then: {
                        properties: {
                            properties: {
                                type: "object",
                                required: ["value"]
                            }
                        }
                    }
                }, {
                    type: "object",
                    if: {
                        properties: {
                            event: {
                                not: {
                                    const: "CompletePayment"
                                }
                            },
                            properties: {
                                type: "object",
                                required: ["currency"]
                            }
                        }
                    },
                    then: {
                        properties: {
                            properties: {
                                type: "object",
                                required: ["value"]
                            }
                        }
                    }
                }]
            };
            function eE(e, {instancePath: t="", parentData: r, parentDataProperty: a, rootData: s=e}={}) {
                let n = null
                  , i = 0;
                if (!(e && "object" == typeof e && !Array.isArray(e)))
                    return eE.errors = [{
                        instancePath: t,
                        schemaPath: "#/allOf/0/type",
                        keyword: "type",
                        params: {
                            type: "object"
                        },
                        message: "must be object",
                        schema: ev.allOf[0].type,
                        parentSchema: ev.allOf[0],
                        data: e
                    }],
                    !1;
                let o = i
                  , p = !0
                  , l = i;
                if (e && "object" == typeof e && !Array.isArray(e)) {
                    if (void 0 === e.event && 1) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    } else if (void 0 !== e.event && "CompletePayment" !== e.event) {
                        let e = {};
                        null === n ? n = [e] : n.push(e),
                        i++
                    }
                }
                var c = l === i;
                if (i = o,
                null !== n && (o ? n.length = o : n = null),
                c) {
                    let r = i;
                    if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                        let r = e.properties
                          , a = i;
                        if (i === a)
                            if (!r || "object" != typeof r || Array.isArray(r))
                                return eE.errors = [{
                                    instancePath: t + "/properties",
                                    schemaPath: "#/allOf/0/then/properties/properties/type",
                                    keyword: "type",
                                    params: {
                                        type: "object"
                                    },
                                    message: "must be object",
                                    schema: ev.allOf[0].then.properties.properties.type,
                                    parentSchema: ev.allOf[0].then.properties.properties,
                                    data: r
                                }],
                                !1;
                            else {
                                let e;
                                if (void 0 === r.value && (e = "value"))
                                    return eE.errors = [{
                                        instancePath: t + "/properties",
                                        schemaPath: "#/allOf/0/then/properties/properties/required",
                                        keyword: "required",
                                        params: {
                                            missingProperty: e
                                        },
                                        message: "must have required property '" + e + "'",
                                        schema: ev.allOf[0].then.properties.properties.required,
                                        parentSchema: ev.allOf[0].then.properties.properties,
                                        data: r
                                    }],
                                    !1
                            }
                    }
                    var c = r === i;
                    p = c
                }
                if (!p) {
                    let r = {
                        instancePath: t,
                        schemaPath: "#/allOf/0/if",
                        keyword: "if",
                        params: {
                            failingKeyword: "then"
                        },
                        message: 'must match "then" schema',
                        schema: ev.allOf[0].if,
                        parentSchema: ev.allOf[0],
                        data: e
                    };
                    return null === n ? n = [r] : n.push(r),
                    i++,
                    eE.errors = n,
                    !1
                }
                var h = 0 === i;
                if (h) {
                    let r = i;
                    if (!(e && "object" == typeof e && !Array.isArray(e)))
                        return eE.errors = [{
                            instancePath: t,
                            schemaPath: "#/allOf/1/type",
                            keyword: "type",
                            params: {
                                type: "object"
                            },
                            message: "must be object",
                            schema: ev.allOf[1].type,
                            parentSchema: ev.allOf[1],
                            data: e
                        }],
                        !1;
                    let a = i
                      , s = !0
                      , o = i;
                    if (e && "object" == typeof e && !Array.isArray(e)) {
                        if (void 0 !== e.event) {
                            let t = i
                              , r = i
                              , a = i;
                            if ("CompletePayment" !== e.event) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            }
                            if (a === i) {
                                let e = {};
                                null === n ? n = [e] : n.push(e),
                                i++
                            } else
                                i = r,
                                null !== n && (r ? n.length = r : n = null);
                            var u = t === i
                        } else
                            var u = !0;
                        if (u)
                            if (void 0 !== e.properties) {
                                let t = e.properties
                                  , r = i;
                                if (i === r)
                                    if (t && "object" == typeof t && !Array.isArray(t)) {
                                        if (void 0 === t.currency && 1) {
                                            let e = {};
                                            null === n ? n = [e] : n.push(e),
                                            i++
                                        }
                                    } else {
                                        let e = {};
                                        null === n ? n = [e] : n.push(e),
                                        i++
                                    }
                                var u = r === i
                            } else
                                var u = !0
                    }
                    var d = o === i;
                    if (i = a,
                    null !== n && (a ? n.length = a : n = null),
                    d) {
                        let r = i;
                        if (e && "object" == typeof e && !Array.isArray(e) && void 0 !== e.properties) {
                            let r = e.properties
                              , a = i;
                            if (i === a)
                                if (!r || "object" != typeof r || Array.isArray(r))
                                    return eE.errors = [{
                                        instancePath: t + "/properties",
                                        schemaPath: "#/allOf/1/then/properties/properties/type",
                                        keyword: "type",
                                        params: {
                                            type: "object"
                                        },
                                        message: "must be object",
                                        schema: ev.allOf[1].then.properties.properties.type,
                                        parentSchema: ev.allOf[1].then.properties.properties,
                                        data: r
                                    }],
                                    !1;
                                else {
                                    let e;
                                    if (void 0 === r.value && (e = "value"))
                                        return eE.errors = [{
                                            instancePath: t + "/properties",
                                            schemaPath: "#/allOf/1/then/properties/properties/required",
                                            keyword: "required",
                                            params: {
                                                missingProperty: e
                                            },
                                            message: "must have required property '" + e + "'",
                                            schema: ev.allOf[1].then.properties.properties.required,
                                            parentSchema: ev.allOf[1].then.properties.properties,
                                            data: r
                                        }],
                                        !1
                                }
                        }
                        var d = r === i;
                        s = d
                    }
                    if (!s) {
                        let r = {
                            instancePath: t,
                            schemaPath: "#/allOf/1/if",
                            keyword: "if",
                            params: {
                                failingKeyword: "then"
                            },
                            message: 'must match "then" schema',
                            schema: ev.allOf[1].if,
                            parentSchema: ev.allOf[1],
                            data: e
                        };
                        return null === n ? n = [r] : n.push(r),
                        i++,
                        eE.errors = n,
                        !1
                    }
                    var h = r === i
                }
                return eE.errors = n,
                0 === i
            }
        },
        1378: function(e, t, r) {
            var a = this && this.__importDefault || function(e) {
                return e && e.__esModule ? e : {
                    default: e
                }
            }
            ;
            Object.defineProperty(t, "__esModule", {
                value: !0
            }),
            t.getDetectionProductMap = t.getIssueMetadataMap = t.ISSUE_DIRECTORY_PATH = void 0;
            var s = a(r(4505))
              , n = a(r(1798));
            t.ISSUE_DIRECTORY_PATH = "/issue_management",
            t.getIssueMetadataMap = function() {
                return n.default
            }
            ,
            t.getDetectionProductMap = function() {
                return s.default
            }
        },
        2254: function(e, t, r) {
            var a = this && this.__createBinding || (Object.create ? function(e, t, r, a) {
                void 0 === a && (a = r);
                var s = Object.getOwnPropertyDescriptor(t, r);
                (!s || ("get"in s ? !t.__esModule : s.writable || s.configurable)) && (s = {
                    enumerable: !0,
                    get: function() {
                        return t[r]
                    }
                }),
                Object.defineProperty(e, a, s)
            }
            : function(e, t, r, a) {
                void 0 === a && (a = r),
                e[a] = t[r]
            }
            )
              , s = this && this.__setModuleDefault || (Object.create ? function(e, t) {
                Object.defineProperty(e, "default", {
                    enumerable: !0,
                    value: t
                })
            }
            : function(e, t) {
                e.default = t
            }
            )
              , n = this && this.__importStar || function(e) {
                if (e && e.__esModule)
                    return e;
                var t = {};
                if (null != e)
                    for (var r in e)
                        "default" !== r && Object.prototype.hasOwnProperty.call(e, r) && a(t, e, r);
                return s(t, e),
                t
            }
              , i = this && this.__spreadArray || function(e, t, r) {
                if (r || 2 == arguments.length)
                    for (var a, s = 0, n = t.length; s < n; s++)
                        !a && s in t || (a || (a = Array.prototype.slice.call(t, 0, s)),
                        a[s] = t[s]);
                return e.concat(a || Array.prototype.slice.call(t))
            }
            ;
            Object.defineProperty(t, "__esModule", {
                value: !0
            }),
            t.validateByProduct = t.GetProductSingleEventIssueList = t.supportedDetectionProducts = t.validateByCustomRule = t.validateByJsonSchema = t.validate = void 0;
            var o = r(1378)
              , p = n(r(833))
              , l = r(6256);
            t.validate = function(e, r) {
                var a = (0,
                o.getIssueMetadataMap)()[e];
                if (!a)
                    throw Error("issueName=".concat(e, " is not found in issueMetadataMap"));
                if (!a.classification)
                    throw Error("issueName=".concat(e, " does not have classification"));
                if ("singleEvent" !== a.classification.issueAggregationLevel)
                    throw Error("this IssueType=".concat(a.classification.issueAggregationLevel, " of issueName=").concat(e, " is not singleEvent"));
                if ("jsonSchema" === a.classification.validationType)
                    return (0,
                    t.validateByJsonSchema)(e, r);
                if ("customValidation" === a.classification.validationType)
                    return (0,
                    t.validateByCustomRule)(e, r);
                throw Error("this ValidationType=".concat(a.classification.validationType, " of issueName=").concat(e, " is unsupported"))
            }
            ,
            t.validateByJsonSchema = function(e, t) {
                var r = null;
                try {
                    r = (0,
                    l.getJsonSchemaValidateMap)()[e]
                } catch (t) {
                    console.log("Failed to get validate function for issue: ".concat(e))
                }
                if (null == r)
                    return console.log("Failed to get validate function for issue: ".concat(e)),
                    {
                        name: e,
                        isValid: !0
                    };
                var a = r(JSON.parse(t))
                  , s = [];
                if (!a && r.errors)
                    for (var n = 0, i = r.errors; n < i.length; n++) {
                        var o = i[n]
                          , p = {
                            path: o.instancePath,
                            value: o.data,
                            desc: o.message,
                            params: "",
                            type: ""
                        };
                        switch (o.keyword) {
                        case "dependencies":
                        case "required":
                            p.type = "miss",
                            p.params = o.params.additionalProperty,
                            p.value = "";
                            break;
                        case "minLength":
                            p.type = "too_short",
                            p.params = null;
                            break;
                        case "maxLength":
                            p.type = "too_long",
                            p.params = null;
                            break;
                        case "type":
                        case "enum":
                            p.type = o.keyword,
                            p.params = o.instancePath.split("/").pop();
                            break;
                        case "additionalProperties":
                            p.type = "addition",
                            p.params = o.params.additionalProperty;
                            break;
                        case "pattern":
                            p.type = "pattern",
                            p.params = o.params.pattern
                        }
                        s.push(p)
                    }
                return {
                    name: e,
                    isValid: a,
                    issueDetails: s
                }
            }
            ,
            t.validateByCustomRule = function(e, t) {
                var r = p.customValidatorMap;
                if (Object.prototype.hasOwnProperty.call(r, e))
                    return r[e].validate(e, t);
                throw Error("Invalid custom issue name=${issueName}")
            }
            ,
            t.supportedDetectionProducts = ["pixelHelper"],
            t.GetProductSingleEventIssueList = function(e) {
                var t = (0,
                o.getDetectionProductMap)()[e];
                if (!t)
                    throw Error("detectionProduct=".concat(e, " is not found in detectionProductMap"));
                var r = t.issues.singleEventIssues || {};
                return i(i([], r.jsonSchemaIssues || [], !0), r.customValidationIssues || [], !0)
            }
            ,
            t.validateByProduct = function(e, r) {
                if (!t.supportedDetectionProducts.includes(e))
                    throw Error("detectionProduct=".concat(e, " is not supported in JavaScript"));
                for (var a = (0,
                t.GetProductSingleEventIssueList)(e), s = !0, n = [], i = 0; i < a.length; i++) {
                    var o = a[i]
                      , p = (0,
                    t.validate)(o, r);
                    p.isValid || (s = !1),
                    n.push(p)
                }
                return [s, n]
            }
        },
        7055: function(e, t) {
            function r(e) {
                let t, r = e.length, a = 0, s = 0;
                for (; s < r; )
                    a++,
                    (t = e.charCodeAt(s++)) >= 55296 && t <= 56319 && s < r && (64512 & (t = e.charCodeAt(s))) == 56320 && s++;
                return a
            }
            t.default = r,
            r.code = 'require("ajv/dist/runtime/ucs2length").default'
        },
        9855: function(e) {
            e.exports = "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHZpZXdCb3g9IjAgMCAxNiAxNiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPHJlY3QgeD0iMSIgeT0iMSIgd2lkdGg9IjE0LjY3IiBoZWlnaHQ9IjE0LjY3IiByeD0iNy4zMzUiIGZpbGw9IiMzNDUxRjciLz4KPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik04LjYzMTg3IDEyLjEwNjJDOC4zNTc1OCAxMi4xMDYyIDguMTM1MjIgMTEuODgzOCA4LjEzNTIyIDExLjYwOTVWNS42NDk4NEM4LjEzNTIyIDUuMzc1NTUgOC4zNTc1OCA1LjE1MzIgOC42MzE4NyA1LjE1MzJDOC45MDYxNSA1LjE1MzIgOS4xMjg1MSA1LjM3NTU1IDkuMTI4NTEgNS42NDk4NFYxMS42MDk1QzkuMTI4NTEgMTEuODgzOCA4LjkwNjE1IDEyLjEwNjIgOC42MzE4NyAxMi4xMDYyWiIgZmlsbD0id2hpdGUiLz4KPHBhdGggZmlsbC1ydWxlPSJldmVub2RkIiBjbGlwLXJ1bGU9ImV2ZW5vZGQiIGQ9Ik01LjI5ODY2IDguOTgwODZDNS4xMDQ3MSA4Ljc4NjkxIDUuMTA0NzEgOC40NzI0NiA1LjI5ODY2IDguMjc4NUw4LjI3ODUgNS4yOTg2NkM4LjQ3MjQ1IDUuMTA0NzEgOC43ODY5MSA1LjEwNDcxIDguOTgwODYgNS4yOTg2NkwxMS45NjA3IDguMjc4NUMxMi4xNTQ3IDguNDcyNDYgMTIuMTU0NyA4Ljc4NjkxIDExLjk2MDcgOC45ODA4NkMxMS43NjY4IDkuMTc0ODEgMTEuNDUyMyA5LjE3NDgxIDExLjI1ODMgOC45ODA4Nkw4LjYyOTY4IDYuMzUyMTlMNi4wMDEwMiA4Ljk4MDg2QzUuODA3MDcgOS4xNzQ4MSA1LjQ5MjYxIDkuMTc0ODEgNS4yOTg2NiA4Ljk4MDg2WiIgZmlsbD0id2hpdGUiLz4KPC9zdmc+Cg=="
        },
        7164: function(e) {
            e.exports = "data:image/svg+xml;base64,PHN2ZyB3aWR0aD0iMTYiIGhlaWdodD0iMTYiIHZpZXdCb3g9IjAgMCAxNiAxNiIgZmlsbD0ibm9uZSIgeG1sbnM9Imh0dHA6Ly93d3cudzMub3JnLzIwMDAvc3ZnIj4KPGNpcmNsZSBjeD0iOC4wMDAxNiIgY3k9IjguMDAwMDQiIHI9IjYuNjY2NjciIGZpbGw9IiMzNDUxRjciIHN0cm9rZT0iIzM0NTFGNyIgc3Ryb2tlLXdpZHRoPSIxLjMzIi8+CjxwYXRoIGQ9Ik03LjY2NjY3IDQuNjY2NzVMNiA4LjAwMDA4SDEwTDguMzMzMzMgMTEuMzMzNCIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIxLjMzIiBzdHJva2UtbGluZWNhcD0icm91bmQiIHN0cm9rZS1saW5lam9pbj0icm91bmQiLz4KPC9zdmc+Cg=="
        },
        9350: function(e, t, r) {
            r.d(t, {
                Ic: () => p,
                Ny: () => s,
                P5: () => a,
                bk: () => o,
                c1: () => n,
                iG: () => i
            });
            let a = 42
              , s = "anonymous_id"
              , n = ["vc_properties"]
              , i = "TiktokAnalyticsObject"
              , o = "ttq"
              , p = /(ads.tiktok.com\/i18n\/events_manager\/v2\/creationFlow)|(byteoversea.net\/i18n\/events_manager\/v2\/creationFlow)/
        },
        3747: function(e, t, r) {
            r.d(t, {
                Fi: () => s,
                d4: () => a
            });
            let a = {
                Pageview: "pageview",
                AddBilling: "add_billing",
                AddPaymentInfo: "add_billing",
                AddToCart: "on_web_cart",
                AddToWishlist: "on_web_add_to_wishlist",
                Browse: "view",
                Checkout: "on_web_order",
                ClickButton: "button",
                ClickForm: "button",
                ClickInConsultationPage: "button",
                ClickInDownloadPage: "button",
                ClickToDownload: "download_start",
                CompletePayment: "shopping",
                CompleteRegistration: "on_web_register",
                Consult: "consult",
                ConsultByPhone: "consult",
                Contact: "consult",
                Download: "download_start",
                InitiateCheckout: "initiate_order",
                PlaceAnOrder: "on_web_order",
                Purchase: "shopping",
                Registration: "on_web_register",
                Search: "on_web_search",
                StartCheckout: "initiate_order",
                SubmitForm: "form",
                Subscribe: "on_web_subscribe",
                ViewConsultationPage: "on_web_detail",
                ViewContent: "on_web_detail",
                ViewDownloadPage: "on_web_detail",
                ViewForm: "on_web_detail"
            }
              , s = {
                Metadata: {
                    displayEventName: "Metadata Automatically Detected",
                    icon: r(7164)
                },
                Click: {
                    displayEventName: "Button Click Automatically Detected",
                    icon: r(9855)
                },
                AutoPageview: {
                    displayEventName: "Pageview Automatically Detected",
                    icon: r(9855)
                }
            }
        },
        1346: function(e, t, r) {
            r.d(t, {
                _: () => n
            });
            var a = r(8069);
            let s = (0,
            a.IH)( () => {
                let e = (0,
                a.Ie)();
                return function(t) {
                    Reflect.defineProperty(self, (0,
                    a.Gp)(), {
                        enumerable: !0,
                        configurable: !0,
                        get: () => e,
                        set(r) {
                            e = r,
                            t && t.forEach(e => {
                                e(r)
                            }
                            )
                        }
                    })
                }
            }
            )()
              , n = ( () => {
                let e = [];
                return s(e),
                t => {
                    e.push(t)
                }
            }
            )()
        },
        5465: function(e, t, r) {
            r.d(t, {
                _R: () => s
            });
            var a, s = ((a = {})[a.UNKNOWN = 0] = "UNKNOWN",
            a[a.HOLD = 1] = "HOLD",
            a[a.REVOKE = 2] = "REVOKE",
            a[a.GRANT = 3] = "GRANT",
            a)
        },
        8797: function(e, t, r) {
            r.d(t, {
                B: () => a
            });
            let a = e => {
                let t = Array.prototype.slice.call(document.getElementsByTagName("script"));
                for (let r = 0; r < t.length; r++) {
                    let a = t[r];
                    if (a.innerHTML && a.innerHTML.indexOf(e) > -1)
                        return a
                }
            }
        },
        8069: function(e, t, r) {
            r.d(t, {
                Bx: () => a.B,
                Gp: () => n.G,
                IH: () => s.IH,
                Ie: () => n.I,
                KK: () => i.KK,
                Sp: () => i.Sp,
                VV: () => i.VV,
                Xh: () => s.Xh,
                _m: () => s._m,
                cT: () => s.cT,
                mc: () => s.G,
                tf: () => s.tf,
                vx: () => s.vx,
                xL: () => s.xL
            });
            var a = r(8797)
              , s = r(9803)
              , n = r(6979)
              , i = r(7971)
        },
        7971: function(e, t, r) {
            r.d(t, {
                KK: () => o,
                Sp: () => i,
                VV: () => n
            });
            let a = e => {
                try {
                    return sessionStorage.getItem(e) || ""
                } catch {
                    return ""
                }
            }
              , s = (e, t) => {
                try {
                    sessionStorage.setItem(e, t)
                } catch {}
            }
              , n = e => {
                try {
                    sessionStorage.removeItem(e)
                } catch (e) {}
            }
              , i = e => {
                try {
                    let t = a(e);
                    return JSON.parse(t)
                } catch (e) {
                    return null
                }
            }
              , o = (e, t) => {
                try {
                    let r = JSON.stringify(t);
                    s(e, r)
                } catch (e) {}
            }
        },
        6979: function(e, t, r) {
            r.d(t, {
                G: () => s,
                I: () => n
            });
            var a = r(9350);
            let s = () => "object" == typeof self && self[a.iG] || a.bk
              , n = () => "object" == typeof self && self[s()]
        },
        9803: function(e, t, r) {
            r.d(t, {
                G: () => y,
                IH: () => o,
                Xh: () => _,
                _m: () => d,
                cT: () => c,
                tf: () => u,
                vx: () => l,
                xL: () => h
            });
            var a = r(3713)
              , s = r(3747)
              , n = r(5465)
              , i = r(6979);
            let o = a.Z
              , p = e => e && e instanceof Object ? JSON.stringify(e).replace(/\"/gi, "'") : "string" == typeof e ? `'${e}'` : e
              , l = (e, t, r) => {
                if ("Pageview" === e)
                    return "";
                let a = "";
                Object.entries(t || {}).forEach( (e, t) => {
                    let[r,s] = e;
                    a += `${0 === t ? `{${r}` : `,${r}`}: ${p(s)}`
                }
                ),
                a ? a = `${a}}` : r && Object.keys(r || {}).length > 0 && (a = "{}");
                let s = "";
                return r && Object.keys(r || {}).length > 0 && Object.entries(r || {}).forEach( (e, t) => {
                    let[r,a] = e;
                    s += `${0 === t ? `{${r}` : `, ${r}`}: ${p(a)}`
                }
                ),
                s && (s = `${s}}`),
                `ttq.track('${e}'${a ? `,${a}` : ""}${s ? `,${s}` : ""})`
            }
              , c = (e, t, r) => "Pageview" === t ? "" : r && r.pixelMethod && "standard" === r.pixelMethod ? "event_builder" : e && e.partner ? e.partner : window.ttq && window.ttq._partner ? window.ttq._partner : "manual"
              , h = e => {
                let t = (0,
                i.I)() || [];
                return (t._o && t._o[e] || {}).limited_data_use
            }
              , u = e => !!s.Fi[e]
              , d = function(e, t, r) {
                var a;
                let s = arguments.length > 3 && void 0 !== arguments[3] ? arguments[3] : {}
                  , n = null == (a = (0,
                i.I)()) ? void 0 : a.context;
                if (n)
                    return n.assemblyData(e, t, r, s)
            }
              , m = () => {
                let e, t = (0,
                i.I)() || [];
                return t && Array.isArray(t) && t.length > 0 && t.forEach(t => {
                    "holdConsent" === t[0] && (e = n._R.HOLD),
                    "revokeConsent" === t[0] && (e = n._R.REVOKE),
                    "grantConsent" === t[0] && (e = n._R.GRANT)
                }
                ),
                e
            }
              , y = function() {
                let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
                i.I)();
                return !!(null == e ? void 0 : e._container)
            }
              , f = () => {
                var e, t, r, a;
                let s = y()
                  , n = (0,
                i.I)() || [];
                return s ? null == (t = n._container) || null == (e = t.get(Symbol.for("CONSENT_SERVICE"))) ? void 0 : e.getConsentMode() : null == (a = n.context) || null == (r = a.consentManager) ? void 0 : r.getConsentMode()
            }
              , _ = () => {
                let e = m();
                return e || (e = f()),
                e
            }
        },
        6129: function(e, t, r) {
            r.d(t, {
                Z: () => a
            });
            let a = function(e) {
                var t = typeof e;
                return null != e && ("object" == t || "function" == t)
            }
        },
        3713: function(e, t, r) {
            r.d(t, {
                Z: () => M
            });
            var a = /\s/;
            let s = function(e) {
                for (var t = e.length; t-- && a.test(e.charAt(t)); )
                    ;
                return t
            };
            var n = /^\s+/
              , i = r(6129)
              , o = "object" == typeof global && global && global.Object === Object && global
              , p = "object" == typeof self && self && self.Object === Object && self
              , l = (o || p || Function("return this")()).Symbol
              , c = Object.prototype
              , h = c.hasOwnProperty
              , u = c.toString
              , d = l ? l.toStringTag : void 0;
            let m = function(e) {
                var t = h.call(e, d)
                  , r = e[d];
                try {
                    e[d] = void 0;
                    var a = !0
                } catch (e) {}
                var s = u.call(e);
                return a && (t ? e[d] = r : delete e[d]),
                s
            };
            var y = Object.prototype.toString
              , f = l ? l.toStringTag : void 0;
            let _ = function(e) {
                return null == e ? void 0 === e ? "[object Undefined]" : "[object Null]" : f && f in Object(e) ? m(e) : y.call(e)
            }
              , g = function(e) {
                return "symbol" == typeof e || null != e && "object" == typeof e && "[object Symbol]" == _(e)
            };
            var v = 0 / 0
              , E = /^[-+]0x[0-9a-f]+$/i
              , A = /^0b[01]+$/i
              , I = /^0o[0-7]+$/i
              , N = parseInt;
            let P = function(e) {
                if ("number" == typeof e)
                    return e;
                if (g(e))
                    return v;
                if ((0,
                i.Z)(e)) {
                    var t, r = "function" == typeof e.valueOf ? e.valueOf() : e;
                    e = (0,
                    i.Z)(r) ? r + "" : r
                }
                if ("string" != typeof e)
                    return 0 === e ? e : +e;
                e = (t = e) ? t.slice(0, s(t) + 1).replace(n, "") : t;
                var a = A.test(e);
                return a || I.test(e) ? N(e.slice(2), a ? 2 : 8) : E.test(e) ? v : +e
            };
            var T = 1 / 0;
            let b = function(e) {
                var t, r = (t = e) ? (t = P(t)) === T || t === -T ? (t < 0 ? -1 : 1) * 17976931348623157e292 : t == t ? t : 0 : 0 === t ? t : 0, a = r % 1;
                return r == r ? a ? r - a : r : 0
            }
              , O = function(e, t) {
                var r;
                if ("function" != typeof t)
                    throw TypeError("Expected a function");
                return e = b(e),
                function() {
                    return --e > 0 && (r = t.apply(this, arguments)),
                    e <= 1 && (t = void 0),
                    r
                }
            }
              , M = function(e) {
                return O(2, e)
            }
        },
        4505: function(e) {
            e.exports = JSON.parse('{"appDiagnosticsPipeline":{"name":"appDiagnosticsPipeline","issues":{"singleEventIssues":{},"otherIssues":["MISS_ACHIEVE_LEVEL_EVENT","MISS_CHECKOUT_EVENT","MISS_INSTALL_EVENT","MISS_LAUNCH_APP_EVENT","MISS_LOGIN_EVENT","MISS_PURCHASE_EVENT","MISS_PURCHASE_EVENT_PARAMETER","MISS_REGISTRATION_EVENT"]}},"overall":{"name":"overall","issues":{"singleEventIssues":{"jsonSchemaIssues":["EMPTY_EVENT_TYPE_NAME","ILLEGAL_EVENT_TYPE_NAME","INVALID_CONTENT_ID","INVALID_CONTENT_TYPE","INVALID_CURRENCY_CODE","INVALID_EMAIL_FORMAT","INVALID_EMAIL_INFORMATION","INVALID_EVENT_PARAMETER_VALUE","INVALID_PHONE_NUMBER_FORMAT","INVALID_PHONE_NUMBER_INFORMATION","LONG_EVENT_TYPE_NAME","MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","MISMATCHED_EVENT_TYPE_NAME_FOR_STANDARD_EVENT","MISSING_CONTENT_ID","MISSING_CURRENCY_PARAMETER","MISSING_EMAIL_AND_PHONE","MISSING_VALUE_PARAMETER"]},"otherIssues":["AAM_OFF","FIRST_PARTY_COOKIE_OFF","LOW_MAM_PII_COVERAGE_FOR_BROWSER","LOW_MAM_PII_COVERAGE_FOR_SERVER","MISMATCHED_EVENT_ID","MISSING_EVENT_ID_FOR_BROWSER","MISSING_EVENT_ID_FOR_SERVER","MISS_ACHIEVE_LEVEL_EVENT","MISS_CHECKOUT_EVENT","MISS_EMAIL_OR_PHONE_NUMBER_PARAMETERS","MISS_INSTALL_EVENT","MISS_LAUNCH_APP_EVENT","MISS_LOGIN_EVENT","MISS_PURCHASE_EVENT","MISS_PURCHASE_EVENT_PARAMETER","MISS_REGISTRATION_EVENT","NO_MAM_PII_FOR_BROWSER","NO_MAM_PII_FOR_BROWSER_AAM_OFF","NO_MAM_PII_FOR_SERVER","SENSIG_DETECTED"]}},"pixelHelper":{"name":"pixelHelper","issues":{"singleEventIssues":{"jsonSchemaIssues":["EMPTY_EVENT_TYPE_NAME","INVALID_CONTENT_ID","INVALID_CONTENT_TYPE","INVALID_CURRENCY_CODE","INVALID_EMAIL_FORMAT","INVALID_EMAIL_INFORMATION","INVALID_EVENT_PARAMETER_VALUE","INVALID_PHONE_NUMBER_FORMAT","INVALID_PHONE_NUMBER_INFORMATION","LONG_EVENT_TYPE_NAME","MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","MISSING_CONTENT_ID","MISSING_CURRENCY_PARAMETER","MISSING_EMAIL_AND_PHONE","MISSING_VALUE_PARAMETER"]}}},"pixelSDK":{"name":"pixelSDK","issues":{"singleEventIssues":{"jsonSchemaIssues":["EMPTY_EVENT_TYPE_NAME","INVALID_CONTENT_ID","INVALID_CONTENT_TYPE","INVALID_CURRENCY_CODE","INVALID_EMAIL_FORMAT","INVALID_EMAIL_INFORMATION","INVALID_EVENT_PARAMETER_VALUE","INVALID_PHONE_NUMBER_FORMAT","INVALID_PHONE_NUMBER_INFORMATION","LONG_EVENT_TYPE_NAME","MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","MISSING_CONTENT_ID","MISSING_CURRENCY_PARAMETER","MISSING_EMAIL_AND_PHONE","MISSING_VALUE_PARAMETER"]}}},"testEvent":{"name":"testEvent","issues":{"singleEventIssues":{"jsonSchemaIssues":["EMPTY_EVENT_TYPE_NAME","ILLEGAL_EVENT_TYPE_NAME","INVALID_CONTENT_ID","INVALID_CONTENT_TYPE","INVALID_CURRENCY_CODE","INVALID_EMAIL_FORMAT","INVALID_EMAIL_INFORMATION","INVALID_EVENT_PARAMETER_VALUE","INVALID_PHONE_NUMBER_FORMAT","INVALID_PHONE_NUMBER_INFORMATION","LONG_EVENT_TYPE_NAME","MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","MISSING_CONTENT_ID","MISSING_CURRENCY_PARAMETER","MISSING_EMAIL_AND_PHONE","MISSING_VALUE_PARAMETER"]}}},"webDiagnosticsPipeline":{"name":"webDiagnosticsPipeline","issues":{"singleEventIssues":{"jsonSchemaIssues":["EMPTY_EVENT_TYPE_NAME","ILLEGAL_EVENT_TYPE_NAME","INVALID_CONTENT_ID","INVALID_CONTENT_TYPE","INVALID_CURRENCY_CODE","INVALID_EMAIL_FORMAT","INVALID_EMAIL_INFORMATION","INVALID_EVENT_PARAMETER_VALUE","INVALID_PHONE_NUMBER_FORMAT","INVALID_PHONE_NUMBER_INFORMATION","LONG_EVENT_TYPE_NAME","MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","MISSING_CONTENT_ID","MISSING_CURRENCY_PARAMETER","MISSING_EMAIL_AND_PHONE","MISSING_VALUE_PARAMETER"]},"otherIssues":["AAM_OFF","FIRST_PARTY_COOKIE_OFF","LOW_MAM_PII_COVERAGE_FOR_BROWSER","LOW_MAM_PII_COVERAGE_FOR_SERVER","MISMATCHED_EVENT_ID","MISSING_EVENT_ID_FOR_BROWSER","MISSING_EVENT_ID_FOR_SERVER","MISS_EMAIL_OR_PHONE_NUMBER_PARAMETERS","NO_MAM_PII_FOR_BROWSER","NO_MAM_PII_FOR_BROWSER_AAM_OFF","NO_MAM_PII_FOR_SERVER","SENSIG_DETECTED"]}}}')
        },
        1798: function(e) {
            e.exports = JSON.parse('{"EMPTY_EVENT_TYPE_NAME":{"name":"EMPTY_EVENT_TYPE_NAME","definition":"If the event name/type is not received, or if it is an empty string or a string that only contains spaces, then surface this issue.","triggerLogic":"If \'event\' parameter is nil or an empty string or a string that only contains spaces, then surface this issue.","jsonSchema":"json_schema/EMPTY_EVENT_TYPE_NAME.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"empty_event_type_name.diagnostics.issue_title","desc":"empty_event_type_name.diagnostics.issue_desc","suggestion":"empty_event_type_name.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?rid=5ipocbxyw8v&id=1701890973258754","referenceDoc":"/docx/SXBad3jw8o9CVqxQMwQuht4KsKE"},"INVALID_CONTENT_ID":{"name":"INVALID_CONTENT_ID","definition":"If the \'content_id\' is received but value is an empty string or or a string that only contains spaces, or if the \'content_ids\' is received but the value is invalid or an array of invalid values (according to definition of content_id), then surface this issue if it doesn\'t meet the requirement.. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'. ","triggerLogic":"If the \'content_id\' is received but value is an empty string or or a string that only contains spaces, or if the \'content_ids\' is received but the value is invalid or an array of invalid values (according to definition of content_id), then surface this issue if it doesn\'t meet the requirement.. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'. ","jsonSchema":"json_schema/INVALID_CONTENT_ID.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_content_id.diagnostics.issue_title","desc":"invalid_content_id.diagnostics.issue_desc","suggestion":"invalid_content_id.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/L31RdGip5onLU1xmjYau8A6dsQh"},"INVALID_CONTENT_TYPE":{"name":"INVALID_CONTENT_TYPE","definition":"\'content_type\' must be either product, product_group, destination, hotel, flight, or vehicle if recevied. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'. Surface this issue if it doesn\'t meet the requirement.","triggerLogic":"\'content_type\' must be either product, product_group, destination, hotel, flight, or vehicle if recevied. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'. Surface this issue if it doesn\'t meet the requirement.","jsonSchema":"json_schema/INVALID_CONTENT_TYPE.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_content_type.diagnostics.issue_title","desc":"invalid_content_type_diagnostics_issue_desc","suggestion":"invalid_content_type.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/SOONdJPmsoIbznxwqd9uI6U1sCc"},"INVALID_CURRENCY_CODE":{"name":"INVALID_CURRENCY_CODE","definition":"If currency code does not match a supported currency code, then surface this issue.","triggerLogic":"Currency code does not match a currency code supported","jsonSchema":"json_schema/INVALID_CURRENCY_CODE.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_currency_code.diagnostics.issue_title","desc":"invalid_currency_code.diagnostics.issue_desc","suggestion":"invalid_currency_code.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/PF1cda170ouEubxCd1wuPGWvssh"},"INVALID_EMAIL_FORMAT":{"name":"INVALID_EMAIL_FORMAT","definition":"Email (\'sha256_email\' or \'email\') is invalid if: 1. If the parameter is \'sha256_email\', it is not a valid sha256 value (not 64 characters of 0-9, a-z, or A-Z), or 2. If the parameter is \'email\', it is not a valid email like \'abc@abc.com\'. Some invalid cases include: missing \'@\' sign (\'abcabc.com\'), missing parts before or after the \'@\' (\'abc@\' or \'@abc.com\'), and invalid domain (\'abc@abc\'). \\nThis does not include \'auto_email\'. This does not include double hashing issues. This does not include filler PII.","triggerLogic":"Check the \'_inspection.identity_params.email_is_hashed\' and \'_inspection.identity_params.sha256_email\'. If any of these contain \'unknown_invalid\', then surface this issue.","jsonSchema":"json_schema/INVALID_EMAIL_FORMAT.json","surfacingProducts":["webDiagnosticTab","testEvent","pixelHelper","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_email_format.diagnostics.issue_title","desc":"invalid_email_format.diagnostics.issue_desc","suggestion":"invalid_email_format.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?id=1739585700402178","referenceDoc":"/docx/UhpGdSEUqoeQWEx6CspuxT7qsQg"},"INVALID_EMAIL_INFORMATION":{"name":"INVALID_EMAIL_INFORMATION","definition":"If email hits the below static filler list, then surface this issue. 20 values we deemed as non-PIIs (aka fillers) due since they meet the criteria below: (a) >1000 pixel event count per day, (b) >100 unique IP address count and (c) paired with >5 unique phone parameters. Such as \'\', NULL, Undefined, etc... \\nJust cover the hard-coding issues. This does not include double hashing issues.","triggerLogic":"Check the \'_inspection.identity_params.email_is_hashed\' and \'_inspection.identity_params.sha256_email\'. If any of these contain \'filter_events\', then surface this issue.","jsonSchema":"json_schema/INVALID_EMAIL_INFORMATION.json","surfacingProducts":["webDiagnosticTab","testEvent","pixelHelper","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_email_information.diagnostics.issue_title","desc":"invalid_email_information.diagnostics.issue_desc","suggestion":"invalid_email_information.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?id=1739585700402178","referenceDoc":"/docx/RCxgddNrxodDQqx95eAu0dKesyg"},"INVALID_EVENT_PARAMETER_VALUE":{"name":"INVALID_EVENT_PARAMETER_VALUE","definition":"The \'value\' format must be either integer (e.g. 100) or follow the decimal number format (e.g. 12.34), which cannot contain currency signs, special characters, letters or commas. If it does not meet decimal number format (integer, contains one \'.\'), then surface this issue.","triggerLogic":"The value field must contain a number greater than or equal to zero, and may not include letters, special characters, currency symbols or commas. Flag If it does not meet the format.","jsonSchema":"json_schema/INVALID_EVENT_PARAMETER_VALUE.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_event_parameter_value.diagnostics.issue_title","desc":"invalid_event_parameter_value.diagnostics.issue_desc","suggestion":"invalid_event_parameter_value.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/GjAAdYJoVoZhrPxsedYuI6J9scg"},"INVALID_PHONE_NUMBER_FORMAT":{"name":"INVALID_PHONE_NUMBER_FORMAT","definition":"Phone format doesnt meet E164 format. \\nThis does _not_ include double hashing issues. This does not include filler PII. ","triggerLogic":"Check the \'_inspection.identity_params.phone_is_hashed\' and \'_inspection.identity_params.sha256_phone\'. If any of these contain \'unknown_invalid\', then surface this issue.","jsonSchema":"json_schema/INVALID_PHONE_NUMBER_FORMAT.json","surfacingProducts":["webDiagnosticTab","testEvent","pixelHelper","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_phone_number_format.diagnostics.issue_title","desc":"invalid_phone_number_format.diagnostics.issue_desc","suggestion":"invalid_phone_number_format.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?id=1739585700402178","referenceDoc":"/docx/C25ldYq8ZocQfsxGLp9u3R5VsVg"},"INVALID_PHONE_NUMBER_INFORMATION":{"name":"INVALID_PHONE_NUMBER_INFORMATION","definition":"If phone number hits the below static filler list, then surface this issue. 20 values we deemed as non-PIIs (aka fillers) due since they meet the criteria below: (a) >1000 pixel event count per day, (b) >100 unique IP address count and (c) paired with >5 unique phone parameters. Such as \'\', NULL, Undefined, etc... \\nJust cover the hard-coding issues. This does _not_ include double hashing issues.","triggerLogic":"Check the \'_inspection.identity_params.phone_is_hashed\' and \'_inspection.identity_params.sha256_phone\'. If any of these contain \'filter_events\', then surface this issue.","jsonSchema":"json_schema/INVALID_PHONE_NUMBER_INFORMATION.json","surfacingProducts":["webDiagnosticTab","testEvent","pixelHelper","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"invalid_phone_number_information.diagnostics.issue_title","desc":"invalid_phone_number_information.diagnostics.issue_desc","suggestion":"invalid_phone_number_information.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?id=1739585700402178","referenceDoc":"/docx/Nr0QdBiDpoeArixmqvSuMAKyshh"},"LONG_EVENT_TYPE_NAME":{"name":"LONG_EVENT_TYPE_NAME","definition":"If the length of event name/type is larger than 50 chars and event type is not an empty string or a string that only contains spaces, then surface this issue.","triggerLogic":"If the length of \'event\' parameter is larger than 50 chars and \'event\' parameter is not an empty string or a string that only contains spaces, then surface this issue.","jsonSchema":"json_schema/LONG_EVENT_TYPE_NAME.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"long_event_type_name.diagnostics.issue_title","desc":"long_event_type_name.diagnostics.issue_desc.singular","descPlural":"long_event_type_name.diagnostics.issue_desc","suggestion":"long_event_type_name.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2&lang=en#anchor-2","referenceDoc":"/docx/DQ4rdW345ok6PYxtKvUuqoTZske"},"MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT":{"name":"MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT","definition":"If the event type is not an empty string or a string that only contains spaces, then the event type should follow the rules below. 1) The string must start with an alphabetic character (a-z or A-Z or digit). 2) The string can have alphanumeric characters (a-z, A-Z, or 0-9), underscores (_), hyphens (-), or whitespaces. 3) The string cannot end with whitespace.","triggerLogic":"If the event type is not an empty string or a string that only contains spaces, check if first_cha != alpha letter or digit OR last_cha = space OR any_event_cha not in (alpha letter, digits, \'_\', \'-\', \' \'), then surface this issue.","jsonSchema":"json_schema/MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT.json","surfacingProducts":["webDiagnosticTab","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"mismatched_event_type_name.diagnostics.issue_title","desc":"mismatched_event_type_name.diagnostics.issue_desc.singular","descPlural":"mismatched_event_type_name.diagnostics.issue_desc","suggestion":"mismatched_event_type_name.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2&lang=en#anchor-2","referenceDoc":"/docx/WSRSdzCnRoedsbxWPxjuHLucsMH"},"MISSING_CONTENT_ID":{"name":"MISSING_CONTENT_ID","definition":"If the \'content_id\' is not received (\'content_id\' parameter is nil) and \'content_ids\' is not received (\'content_ids\' parameter is nil, or is an array of length 0), then surface this issue. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'.","triggerLogic":"If the \'content_id\' is not received (\'content_id\' parameter is nil) and \'content_ids\' is not received (\'content_ids\' parameter is nil, or is an array of length 0), then surface this issue. Applies to ecommerce event_types: \'CompletePayment\', \'InitiateCheckout\',  \'AddToCart\', \'PlaceAnOrder\',\'ViewContent\', \'AddToWishlist\'.","jsonSchema":"json_schema/MISSING_CONTENT_ID.json","surfacingProducts":["webDiagnosticTab","eventLevelHealthReport","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"missing_content_id_parameter.diagnostics.issue_title","desc":"missing_content_id_parameter.diagnostics.issue_desc","suggestion":"missing_content_id_parameter.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/Rmc3dLEITo3hjrx2wjTuEj5usGg"},"MISSING_CURRENCY_PARAMETER":{"name":"MISSING_CURRENCY_PARAMETER","definition":"For \'CompletePayment\' events: if \'currency\' parameter is not received, then surface this issue; For other events: if there\'s a \'value\' parameter but \'currency\' parameter is not received, then surface this issue.","triggerLogic":"For \'properties.event\' = \'CompletePayment\' events, if \'properties.currency\' parameter is null, then surface this issue. For \'properties.event\' != \'CompletePayment\' events, if there\'s a \'properties.value\' parameter but the \'properties.currency\' parameter is null, then surface this issue.","jsonSchema":"json_schema/MISSING_CURRENCY_PARAMETER.json","surfacingProducts":["webDiagnosticTab","eventLevelHealthReport","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"missing_currency_parameter.diagnostics.issue_title","desc":"missing_currency_parameter.diagnostics.issue_desc","suggestion":"missing_currency_parameter.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/FhRadPI3coIib3x9DFTuBlRHsDd"},"MISSING_EMAIL_AND_PHONE":{"name":"MISSING_EMAIL_AND_PHONE","definition":"For \'Shopping(CompletePayment)\' event only, if event misses email and phone, report this issue. ","triggerLogic":"For \'Shopping(CompletePayment)\' event only, check the \'_inspection.identity_params.phone_is_hashed\', \'_inspection.identity_params.sha256_phone\',  \'_inspection.identity_params.email_is_hashed\' and \'_inspection.identity_params.sha256_email\'. If all of these contain \'empty_value\', then surface this issue.","jsonSchema":"json_schema/MISSING_EMAIL_AND_PHONE.json","surfacingProducts":["webDiagnosticTab","eventLevelHealthReport","testEvent","pixelHelper","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"missing_email_and_phone.diagnostics.issue_title","desc":"missing_email_and_phone.diagnostics.issue_desc","suggestion":"missing_email_and_phone.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/marketing_api/docs?rid=5ipocbxyw8v&id=1701890972946433","referenceDoc":"/docx/KHnSdXkhfoh5Tcxw1AzuTfifsMd"},"MISSING_VALUE_PARAMETER":{"name":"MISSING_VALUE_PARAMETER","definition":"For \'CompletePayment\' events: if \'value\' parameter is not received, then surface this issue; For other events: if there\'s a \'currency\' parameter but \'value\' parameter is not received, then surface this issue.","triggerLogic":"For \'properties.event\' = \'CompletePayment\' events, if \'properties.value\' parameter is null, then surface this issue. For \'properties.event\' != \'CompletePayment\' events, if there\'s a \'properties.currency\' parameter but the \'properties.value\' parameter is null, then surface this issue.","jsonSchema":"json_schema/MISSING_VALUE_PARAMETER.json","surfacingProducts":["webDiagnosticTab","eventLevelHealthReport","pixelHelper","testEvent","pixelSDK"],"classification":{"issueAggregationLevel":"singleEvent","validationType":"jsonSchema"},"tags":{},"uxText":{"title":"missing_value_parameter.diagnostics.issue_title","desc":"missing_value_parameter.diagnostics.issue_desc","suggestion":"missing_value_parameter.diagnostics.issue_solution"},"helpCenterLink":"https://ads.tiktok.com/help/article/standard-events-parameters?redirected=2","referenceDoc":"/docx/UuFld2zHAopEUBxb0a2umPOdsDf"}}')
        }
    }
      , t = {};
    function r(a) {
        var s = t[a];
        if (void 0 !== s)
            return s.exports;
        var n = t[a] = {
            exports: {}
        };
        return e[a].call(n.exports, n, n.exports, r),
        n.exports
    }
    r.d = (e, t) => {
        for (var a in t)
            r.o(t, a) && !r.o(e, a) && Object.defineProperty(e, a, {
                enumerable: !0,
                get: t[a]
            })
    }
    ,
    r.o = (e, t) => Object.prototype.hasOwnProperty.call(e, t),
    r.rv = () => "1.3.4",
    r.ruid = "bundler=rspack@1.3.4",
    ( () => {
        var e = r(6129)
          , t = function(e) {
            return e[e.GET_DOM_CONTENT_LOADED_TS = 0] = "GET_DOM_CONTENT_LOADED_TS",
            e[e.DOM_CONTENT_LOADED = 1] = "DOM_CONTENT_LOADED",
            e[e.TTQ_INITIALIZED = 2] = "TTQ_INITIALIZED",
            e[e.PIXEL_EVENT_SEND = 3] = "PIXEL_EVENT_SEND",
            e[e.ACT_EVENT_SEND = 4] = "ACT_EVENT_SEND",
            e[e.GET_SENDED_EVENTS = 5] = "GET_SENDED_EVENTS",
            e[e.SEND_ANALYTICS_EVENT = 6] = "SEND_ANALYTICS_EVENT",
            e
        }({})
          , a = r(1346);
        let s = (e, t) => {
            let r = Object.assign({
                type: e,
                detail: t
            }, {
                _from: "child"
            });
            window !== window.top ? window.parent && window.parent.postMessage(r, "*") : window.postMessage(r, "*")
        }
        ;
        (0,
        a._)(r => {
            let a = !1;
            r && (0,
            e.Z)(r) && Reflect.defineProperty(r, "initialize", {
                enumerable: !0,
                configurable: !0,
                get: () => a,
                set(e) {
                    a = e,
                    s(t.TTQ_INITIALIZED, {
                        timestamp: Date.now(),
                        domContentLoadedEventStart: performance.timing.domContentLoadedEventStart,
                        domContentLoadedEventEnd: performance.timing.domContentLoadedEventEnd
                    })
                }
            })
        }
        )
    }
    )(),
    ( () => {
        function e(e, t, r) {
            return t in e ? Object.defineProperty(e, t, {
                value: r,
                enumerable: !0,
                configurable: !0,
                writable: !0
            }) : e[t] = r,
            e
        }
        var t = function(e) {
            return e[e.Inject = 0] = "Inject",
            e[e.ContentScript = 1] = "ContentScript",
            e[e.Popup = 2] = "Popup",
            e[e.Background = 3] = "Background",
            e
        }({})
          , a = function(e) {
            return e.Pixel = "TikTokPixelDetailInfo",
            e.Event = "TikTokPixelEvent",
            e.API = "TikTokPixelAPI",
            e.PixelError = "TikTokPixelError",
            e.EventError = "TikTokPixelEventError",
            e.PageError = "TikTokPixelPageError",
            e.Store = "TikTokPixelStore",
            e.SPA = "TikTokPixelSPAMonitor",
            e.FirstPartyCookie = "TikTokFirstPartyCookie",
            e.PixelRequest = "TikTokPixelRequest",
            e.ReportStatus = "TikTokReportStatus",
            e.GetInitialData = "TikTokGetInitialData",
            e.TTPixelHelperUpdate = "TTPixelHelperUpdate",
            e
        }({})
          , s = function(e) {
            return e[e.Live = 0] = "Live",
            e[e.NoRecord = 1] = "NoRecord",
            e
        }({});
        class n {
            constructor(t, r) {
                e(this, "type", void 0),
                e(this, "handler", void 0),
                this.type = t,
                this.register(),
                this.handler = r
            }
        }
        var i = r(8069)
          , o = r(1346);
        let p = function(e) {
            let t = arguments.length > 1 && void 0 !== arguments[1] ? arguments[1] : "setPixelInfo"
              , r = arguments.length > 2 ? arguments[2] : void 0;
            return new Proxy(e,{
                get(e, a) {
                    let s = e[a];
                    return a === t && r ? function() {
                        for (var t = arguments.length, a = Array(t), n = 0; n < t; n++)
                            a[n] = arguments[n];
                        return r.forEach(t => {
                            t(e, ...a)
                        }
                        ),
                        s.apply(e, a)
                    }
                    : s
                },
                set: (e, t, r) => (e[t] = r,
                !0)
            })
        }
          , l = (e, t) => new Proxy(e,{
            get: (e, t) => e[t],
            set: (e, r, a) => (e[r] = p(a, "setPixelInfo", t),
            !0)
        })
          , c = (0,
        i.IH)( (e, t, r) => {
            let a = e[t];
            a && (e[t] = l(a, r))
        }
        )
          , h = (0,
        i.IH)( (e, t) => {
            let r = e;
            r && (e = l(r, t))
        }
        )
          , u = function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 && void 0 !== arguments[1] ? arguments[1] : "pixelMap"
              , r = arguments.length > 2 ? arguments[2] : void 0
              , a = e && e.context && e.context.data;
            a && a[t] && c(a, t, r)
        }
          , d = function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 ? arguments[1] : void 0
              , r = e && e.reporters;
            r && r && h(r, t)
        }
          , m = ( () => {
            let e = [];
            return (0,
            i.mc)() ? (0,
            o._)(d.bind(null, (0,
            i.Ie)(), e)) : (0,
            o._)(u.bind(null, (0,
            i.Ie)(), "pixelMap", e)),
            t => {
                e.push(t)
            }
        }
        )();
        class y {
            defined() {
                y.watch.add(this)
            }
            notify() {
                this.subs.forEach(e => {
                    if ("function" == typeof e.update)
                        try {
                            e.update.apply(e)
                        } catch (e) {
                            console.error(e)
                        }
                }
                )
            }
            constructor() {
                e(this, "subs", void 0),
                this.subs = []
            }
        }
        e(y, "watch", void 0),
        y.watch = null;
        class f {
            add(e) {
                e.subs.push(this)
            }
            update() {
                (0,
                this.callBack)(this.name)
            }
            constructor(t, r) {
                e(this, "name", void 0),
                e(this, "callBack", void 0),
                this.name = t,
                this.callBack = r
            }
        }
        let _ = function() {
            let e = new y;
            return function(t) {
                let r = arguments.length > 1 && void 0 !== arguments[1] ? arguments[1] : () => {}
                ;
                if ("historychange" === t)
                    return function(t, r) {
                        y.watch = new f(t,r),
                        e.defined(),
                        y.watch = null
                    }
                    ;
                if ("pushState" === t || "replaceState" === t) {
                    let a = history[t];
                    return function() {
                        for (var t = arguments.length, s = Array(t), n = 0; n < t; n++)
                            s[n] = arguments[n];
                        r(),
                        a.apply(history, s),
                        e.notify()
                    }
                }
            }
        }()
          , g = e => {
            window.addHistoryListener = _("historychange"),
            history.pushState = _("pushState", e),
            history.replaceState = _("replaceState", e),
            window.addHistoryListener && window.addHistoryListener("history", function() {
                e()
            })
        }
          , v = (0,
        i.IH)( (e, t) => {
            let r = e.track;
            e.track = function() {
                for (var a = arguments.length, s = Array(a), n = 0; n < a; n++)
                    s[n] = arguments[n];
                let i = r.apply(e, s);
                return t && t.forEach(e => {
                    e(...s)
                }
                ),
                i
            }
        }
        )
          , E = (0,
        i.IH)( (e, t) => {
            let r = e.report;
            e.report = function() {
                for (var a = arguments.length, s = Array(a), n = 0; n < a; n++)
                    s[n] = arguments[n];
                let i = r.apply(e, s);
                return t && t.forEach(e => {
                    e(...s)
                }
                ),
                i
            }
        }
        )
          , A = function() {
            var e;
            let t = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , r = arguments.length > 1 ? arguments[1] : void 0
              , a = null == t || null == (e = t.context) ? void 0 : e.methods;
            a && a.track && v(a, r)
        }
          , I = function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 ? arguments[1] : void 0;
            if ((0,
            i.mc)(e))
                E(e._container.get(Symbol.for("REPORT_SERVICE")), t);
            else {
                var r;
                let a = null == e || null == (r = e.context) ? void 0 : r.reportService;
                if (!a || !a.report) {
                    e.context && Reflect.defineProperty(e.context, "reportService", {
                        enumerable: !0,
                        configurable: !0,
                        get: () => a,
                        set(e) {
                            E(a = e, t)
                        }
                    });
                    return
                }
                E(a, t)
            }
        }
          , N = function(e) {
            var t, r;
            let a = arguments.length > 1 && void 0 !== arguments[1] ? arguments[1] : (0,
            i.Ie)();
            if ((0,
            i.mc)(a))
                return null == (r = a._container.get(Symbol.for("TTQ_REPORTERS"))) ? void 0 : r.find(t => t.id === e);
            let s = null == a ? void 0 : a.context;
            return null == s || null == (t = s.pixels) ? void 0 : t.find(t => t.pixelCode === e)
        }
          , P = e => {
            let t = (0,
            i.Ie)()
              , r = t && t.context
              , a = N(e)
              , s = r && r.getUserInfo ? r.getUserInfo() : {}
              , n = r && r.getUserFormatInfo ? r.getUserFormatInfo() : {}
              , o = {};
            return a && (o = a.partner && "None" !== a.partner ? a.advancedMatchingAvailableProperties || {} : {
                email: !0,
                phone_number: !0
            },
            ["first_name", "last_name", "city", "state", "country", "zip_code"].forEach(e => {
                o[e] = !!a.advancedMatchingAvailableProperties && void 0 !== a.advancedMatchingAvailableProperties[e] && a.advancedMatchingAvailableProperties[e]
            }
            )),
            Object.keys(o).reduce( (e, t) => "phone_number" === t || "email" === t || "first_name" === t || "last_name" === t || "city" === t || "state" === t || "country" === t || "zip_code" === t ? Object.assign(e, {
                [t]: {
                    value: s[t],
                    format: n[t] || ["empty_value"]
                }
            }) : e, {})
        }
          , T = () => {
            let e = (0,
            i.Ie)()
              , t = e && e.context
              , r = t && t.getUserInfo ? t.getUserInfo() : {};
            return Object.keys(r).reduce( (e, t) => "phone_number" === t || "email" === t || "first_name" === t || "last_name" === t || "city" === t || "state" === t || "country" === t || "zip_code" === t ? Object.assign(e, {
                [t]: r[t]
            }) : e, {})
        }
          , b = function() {
            var e;
            let t = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)();
            if ((0,
            i.mc)(t))
                return t.reporters.map(e => ({
                    code: e.reporterInfo.pixelCode,
                    name: e.reporterInfo.name,
                    advertiserID: e.reporterInfo.advertiserID,
                    setupMethod: e.reporterInfo.partner || e.reporterInfo.setupMode
                }));
            let r = null == t ? void 0 : t.context;
            return null == r || null == (e = r.pixels) ? void 0 : e.map(e => ({
                code: e.pixelCode,
                name: e.name,
                advertiserID: e.advertiserID,
                setupMethod: e.partner || e.setupMode
            }))
        }
          , O = ( () => {
            let e = [];
            return (0,
            o._)(A.bind(null, (0,
            i.Ie)(), e)),
            t => {
                e.push(t)
            }
        }
        )()
          , M = ( () => {
            let e = [];
            return (0,
            o._)(I.bind(null, (0,
            i.Ie)(), e)),
            t => {
                e.push(t)
            }
        }
        )()
          , S = (0,
        i.IH)( (e, t, r, a) => {
            Reflect.defineProperty(e, t, {
                get: () => function() {
                    for (var t = arguments.length, s = Array(t), n = 0; n < t; n++)
                        s[n] = arguments[n];
                    return a && a.forEach(e => {
                        e(...s)
                    }
                    ),
                    r.apply(e, s)
                }
                ,
                set() {}
            })
        }
        )
          , D = function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 ? arguments[1] : void 0
              , r = arguments.length > 2 ? arguments[2] : void 0
              , a = e[t];
            a && S(e, t, a, r)
        }
          , j = ( () => {
            let e = {};
            return (t, r) => {
                e[t] ? e[t].push(r) : (e[t] = [],
                e[t].push(r),
                (0,
                o._)(D.bind(null, (0,
                i.Ie)(), t, e[t])))
            }
        }
        )()
          , R = (e, t) => new Proxy(e,{
            get: (e, t) => e[t],
            set: (e, r, a) => (e[r] = a,
            t && t.forEach(t => {
                t(e)
            }
            ),
            !0)
        })
          , w = (0,
        i.IH)( (e, t, r) => {
            let a = e[t];
            a && (e[t] = R(a, r))
        }
        )
          , L = function() {
            let e, t = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)(), r = arguments.length > 1 && void 0 !== arguments[1] ? arguments[1] : "userInfo", a = arguments.length > 2 ? arguments[2] : void 0;
            (e = (0,
            i.mc)() ? t && t.context : t && t.context && t.context.data) && e[r] && w(e, r, a)
        }
          , C = ( () => {
            let e = [];
            return (0,
            o._)(L.bind(null, (0,
            i.Ie)(), "userInfo", e)),
            t => {
                e.push(t)
            }
        }
        )();
        var k = r(5465);
        let V = "tt_helper_hold_messages"
          , x = "tt_helper_dedupe_hold_messages";
        class $ {
            setConsentMode(e) {
                switch (this.consentMode = e,
                this.consentMode) {
                case k._R.REVOKE:
                    this.cleanQueue();
                    break;
                case k._R.GRANT:
                    this.releaseQueue(),
                    this.cleanQueue();
                case k._R.HOLD:
                case k._R.UNKNOWN:
                }
            }
            getConsentMode() {
                return this.consentMode
            }
            cacheMessage(e, t) {
                if (null !== t) {
                    if (this.dedupeMap[t])
                        return;
                    this.dedupeMap[t] = !0
                }
                this.queue.push(e),
                this.updateCache()
            }
            isDeduplicated(e) {
                return !!this.dedupeMap[e]
            }
            cleanQueue() {
                this.queue = [],
                (0,
                i.VV)(V),
                (0,
                i.VV)(x)
            }
            updateCache() {
                this.queue && this.queue.length > 0 && ((0,
                i.KK)(V, this.queue),
                (0,
                i.KK)(x, this.dedupeMap))
            }
            releaseQueue() {
                this.dedupeMap = {},
                this.queue.forEach(e => {
                    this.sendMessageHandler(e)
                }
                )
            }
            constructor(t) {
                e(this, "queue", []),
                e(this, "dedupeMap", {}),
                e(this, "consentMode", k._R.UNKNOWN),
                e(this, "sendMessageHandler", void 0),
                this.sendMessageHandler = t;
                let r = (0,
                i.Sp)(V)
                  , a = (0,
                i.Sp)(x);
                Array.isArray(r) && (this.queue = r),
                a && Object.keys(a).length > 0 && (this.dedupeMap = a);
                let s = (0,
                i.Xh)();
                null !== s && this.setConsentMode(s)
            }
        }
        let F = ( () => {
            let e = (0,
            i.IH)( (e, t) => {
                let r = e.setConsentMode;
                e.setConsentMode = function() {
                    for (var a = arguments.length, s = Array(a), n = 0; n < a; n++)
                        s[n] = arguments[n];
                    let i = r.apply(e, s);
                    return t && t.forEach(e => {
                        e(...s)
                    }
                    ),
                    i
                }
            }
            )
              , t = [];
            return (0,
            o._)((function() {
                var t, r;
                let a, s = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
                i.Ie)(), n = arguments.length > 1 ? arguments[1] : void 0;
                if (!(a = (0,
                i.mc)() ? null == (t = s._container) ? void 0 : t.get(Symbol.for("CONSENT_SERVICE")) : null == s || null == (r = s.context) ? void 0 : r.consentManager) || !a.setConsentMode) {
                    s.context && Reflect.defineProperty(s.context, "consentManager", {
                        enumerable: !0,
                        configurable: !0,
                        get: () => a,
                        set(t) {
                            e(a = t, n)
                        }
                    });
                    return
                }
                e(a, n)
            }
            ).bind(null, (0,
            i.Ie)(), t)),
            e => {
                t.push(e)
            }
        }
        )()
          , U = (0,
        i.IH)(function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 ? arguments[1] : void 0
              , r = arguments.length > 2 ? arguments[2] : void 0
              , a = new Proxy(t,{
                get: (e, t) => e[t],
                set(e, t, a, s) {
                    if (a.track) {
                        let e = a.track.bind(a);
                        a.track = function() {
                            for (var t = arguments.length, s = Array(t), n = 0; n < t; n++)
                                s[n] = arguments[n];
                            return r && "EnrichAM" !== s[0] && r.forEach(e => {
                                e(a.getReporterId(), ...s)
                            }
                            ),
                            e(...s)
                        }
                    }
                    return Reflect.set(e, t, a, s)
                }
            });
            e && e._container && e._container.rebind(Symbol.for("TTQ_REPORTERS")).toConstantValue(a)
        })
          , H = function() {
            let e = arguments.length > 0 && void 0 !== arguments[0] ? arguments[0] : (0,
            i.Ie)()
              , t = arguments.length > 1 ? arguments[1] : void 0;
            if (!(0,
            i.mc)(e))
                return;
            let r = e._container.get(Symbol.for("TTQ_REPORTERS"));
            U(e, r, t)
        }
          , G = ( () => {
            let e = [];
            return (0,
            o._)(H.bind(null, (0,
            i.Ie)(), e)),
            t => {
                e.push(t)
            }
        }
        )();
        class Y extends n {
            sendMessage(e) {
                this.beforeSendMessage(e) && (window !== window.top ? window.parent && window.parent.postMessage(Object.assign(e, {
                    _from: "child"
                }), "*") : window.postMessage(e, "*"))
            }
            consentUpdateHandler() {
                let e = (0,
                i.Xh)();
                this.consentManager.setConsentMode(e)
            }
            register() {}
            beforeSendMessage(e) {
                let t = (0,
                i.Xh)();
                return t !== k._R.REVOKE && (t === k._R.HOLD ? (this.consentManager.cacheMessage(e, e.dedupeID),
                !1) : !this.shouldDedupeMessage(e))
            }
            shouldDedupeMessage(e) {
                if (e.dedupeID) {
                    if (this.dedupeQueue.indexOf(e.dedupeID) > -1 || this.consentManager.isDeduplicated(e.dedupeID))
                        return !0;
                    this.dedupeQueue.push(e.dedupeID)
                }
                return !1
            }
            constructor() {
                super(t.Inject),
                e(this, "dedupeQueue", []),
                e(this, "consentManager", void 0),
                this.consentManager = new $(this.sendMessage.bind(this))
            }
        }
        var B = r(9350);
        let q = e => {
            let t = e.parentElement;
            return !!t && ("HEAD" === t.tagName || q(t))
        }
          , K = () => {
            let e = performance.getEntriesByType("resource");
            return !!(e && Array.isArray(e)) && e.some(e => /^http(s)?:\/\/www.googletagmanager.com/.test(e.name))
        }
          , Z = (e, t) => {
            let r = [document.body]
              , a = 0;
            for (; a < e && r.length; ) {
                let e = r.pop();
                if (e === t)
                    return !0;
                if (a++,
                "object" == typeof e && e.children)
                    for (let t = e.children.length; t >= 0; t--)
                        r.push(e.children[t])
            }
            return !1
        }
          , z = e => Z(10, e)
          , W = ( () => {
            let e = [];
            return function(t) {
                return e.push(t),
                e.filter(e => e === t).length > 1
            }
        }
        )()
          , Q = e => e.status === s.Live;
        var J = r(769)
          , X = r(3747);
        let ee = (e, t, r) => {
            let {pixelCode: s, eventType: n, timestamp: i} = t;
            return e.map(e => {
                let {issueDetails: t} = e;
                switch (e.name) {
                case "EMPTY_EVENT_TYPE_NAME":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "empty_event_type",
                            pixelCode: s,
                            eventType: n,
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "LONG_EVENT_TYPE_NAME":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "long_event_type_name",
                            pixelCode: s,
                            eventType: n,
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "MISMATCHED_EVENT_TYPE_NAME_FOR_CUSTOM_EVENT":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "invalid_event_type",
                            pixelCode: s,
                            eventType: n,
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_CONTENT_ID":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_type_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "content_id",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_CONTENT_TYPE":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_type_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "content_type",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_EVENT_PARAMETER_VALUE":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_type_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "value",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_CURRENCY_CODE":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_type_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "currency",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_EMAIL_FORMAT":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_format_err",
                            pixelCode: s,
                            eventType: n,
                            params: "email",
                            eventTimestamp: i,
                            issue_type: "INVALID_PII_FORMAT",
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_EMAIL_INFORMATION":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_format_err",
                            pixelCode: s,
                            eventType: n,
                            params: "email",
                            eventTimestamp: i,
                            issue_type: "INVALID_PII_INFORMATION",
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_PHONE_NUMBER_FORMAT":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_format_err",
                            pixelCode: s,
                            eventType: n,
                            params: "phone_number",
                            eventTimestamp: i,
                            issue_type: "INVALID_PII_FORMAT",
                            issueMetadata: r[e.name]
                        }
                    };
                case "INVALID_PHONE_NUMBER_INFORMATION":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_format_err",
                            pixelCode: s,
                            eventType: n,
                            params: "phone_number",
                            eventTimestamp: i,
                            issue_type: "INVALID_PII_INFORMATION",
                            issueMetadata: r[e.name]
                        }
                    };
                case "MISSING_CONTENT_ID_PARAMETER":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_miss_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "content_id",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "MISSING_CURRENCY_PARAMETER":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_miss_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "currency",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                case "MISSING_EMAIL_AND_PHONE":
                    return {
                        type: a.PixelError,
                        detail: {
                            type: "empty_pii",
                            pixelCode: s,
                            pixelName: "",
                            issueMetadata: r[e.name]
                        }
                    };
                case "MISSING_VALUE_PARAMETER":
                    return {
                        type: a.EventError,
                        detail: {
                            type: "params_miss_err",
                            pixelCode: s,
                            eventType: n,
                            path: t && t[0] && t[0].path ? t[0].path : "/properties",
                            params: "value",
                            eventTimestamp: i,
                            issueMetadata: r[e.name]
                        }
                    };
                default:
                    return
                }
            }
            ).filter(e => e)
        }
          , et = (e, t) => {
            let[r,a] = (0,
            J.validateByProduct)("pixelHelper", JSON.stringify(t))
              , s = (0,
            J.getIssueMetadataMap)();
            return r ? [] : ee(a.filter(e => !e.isValid), e, s)
        }
          , er = ( () => {
            let e = [];
            return function(t) {
                let r = e.filter(e => "Pageview" !== e.eventType).some(e => !["pageview", "on_web_detail"].includes(X.d4[t.eventType]) && t.pixelCode === e.pixelCode && t.timestamp - e.timestamp <= B.P5);
                return e.push(t),
                r
            }
        }
        )()
          , ea = []
          , es = []
          , en = e => es.some(t => t.detail.pixelCode === e)
          , ei = e => (t, r) => {
            let s;
            ea.push(t.pixelCode);
            let n = Date.now() - performance.timing.navigationStart
              , o = (0,
            i.mc)();
            s = o ? {
                code: t.reporterInfo.pixelCode,
                name: t.reporterInfo.name,
                status: t.reporterInfo.status,
                setupMethod: t.reporterInfo.partner || t.reporterInfo.setupMode,
                setupMode: t.reporterInfo.setupMode,
                advertiserID: t.reporterInfo.advertiserID,
                loadTime: 0,
                timeToNavigationStart: n,
                partner: t.reporterInfo.partner,
                is_onsite: !1,
                firstPartyCookieEnabled: t.reporterInfo.firstPartyCookieEnabled
            } : {
                code: t.pixelCode,
                name: r.name,
                status: r.status,
                setupMethod: r.partner || r.setupMode,
                setupMode: r.setupMode,
                advertiserID: r.advertiserID,
                loadTime: 0,
                timeToNavigationStart: n,
                partner: r.partner,
                is_onsite: !1,
                firstPartyCookieEnabled: r.firstPartyCookieEnabled
            };
            let p = {
                type: a.Pixel,
                detail: s
            };
            e.sendMessage(p);
            let l = o ? t.reporterInfo.pixelCode : t.pixelCode
              , c = (0,
            i.Bx)(l);
            if (c) {
                if (!q(c) && !z(c) && !K()) {
                    let t = {
                        type: a.PixelError,
                        detail: {
                            type: "not_in_head",
                            pixelCode: l,
                            pixelName: ""
                        }
                    };
                    !en(l) && o ? (es.push(t),
                    e.sendMessage(t)) : o || e.sendMessage(t)
                }
                if (!Q(s)) {
                    let t = {
                        type: a.PixelError,
                        detail: {
                            type: "invalid_pixel_id",
                            pixelCode: l,
                            pixelName: ""
                        }
                    };
                    !en(l) && o ? (es.push(t),
                    e.sendMessage(t)) : o || e.sendMessage(t)
                }
            }
        }
          , eo = e => (t, r, s, n) => {
            let o = (0,
            i.mc)()
              , p = N(t);
            ea.includes(t) || ei(e)(p, p);
            let l = P(t);
            n && void 0 !== n._i && delete n._i;
            let c = Date.now()
              , h = {
                name: p.name,
                advertiserID: p.advertiserID,
                eventType: r,
                pixelCode: t,
                properties: s,
                AMSetting: l,
                AMParams: T(),
                setupMode: p.partner || p.setupMode,
                pageURL: location.href,
                timestamp: c,
                loadTime: 0,
                timeToNavigationStart: Date.now() - performance.timing.navigationStart,
                code: (0,
                i.vx)(r, s, n),
                eventTrigger: (0,
                i.cT)(p, r, s),
                inspection: {}
            }
              , u = (0,
            i.xL)(t);
            s && void 0 !== s.limited_data_use && (u = !!s.limited_data_use),
            void 0 !== u && (h.ldu = u),
            s && s instanceof Object && 0 === Object.keys(s).length && Object.assign(h, {
                properties: void 0
            }),
            s && "standard" === s.pixelMethod && delete h.properties;
            let d = {
                type: a.Event,
                detail: h
            };
            if (e.sendMessage(d),
            er(h)) {
                let s = {
                    type: a.EventError,
                    detail: {
                        type: "multiple_events",
                        pixelCode: t,
                        eventType: r,
                        eventTimestamp: c
                    }
                };
                e.sendMessage(s)
            }
            let m = et(h, o ? p.assemblyData(t, r, s, n) : (0,
            i._m)(t, r, s, n));
            m.length > 0 && m.forEach(t => {
                e.sendMessage(t)
            }
            )
        }
          , ep = e => (t, r, s) => {
            let n;
            if (-1 === t.indexOf("/pixel/act") || "Pf" === r.action)
                return;
            let {event: o, action: p, properties: l, auto_collected_properties: c, context: h, message_id: u} = r || {}
              , d = h && h.pixel && h.pixel.code || ""
              , m = h && h.pixel && h.pixel.codes || "";
            n = m ? m.split("|") : [d];
            let y = (0,
            i.mc)();
            n.forEach(t => {
                let r, s = N(t);
                ea.includes(t) || ei(e)(s, s);
                let n = P(t)
                  , h = Date.now();
                if (r = y ? {
                    name: s.reporterInfo.name,
                    advertiserID: s.reporterInfo.advertiserID,
                    eventType: o || p,
                    pixelCode: t,
                    properties: l,
                    AMSetting: n,
                    AMParams: T(),
                    setupMode: s.reporterInfo.partner || s.reporterInfo.setupMode,
                    pageURL: location.href,
                    timestamp: h,
                    loadTime: 0,
                    timeToNavigationStart: Date.now() - performance.timing.navigationStart,
                    code: o && (0,
                    i.vx)(o, l, {}),
                    eventTrigger: (0,
                    i.cT)(s, o, l)
                } : {
                    name: s.name,
                    advertiserID: s.advertiserID,
                    eventType: o || p,
                    pixelCode: t,
                    properties: l,
                    AMSetting: n,
                    AMParams: T(),
                    setupMode: s.partner || s.setupMode,
                    pageURL: location.href,
                    timestamp: h,
                    loadTime: 0,
                    timeToNavigationStart: Date.now() - performance.timing.navigationStart,
                    code: o && (0,
                    i.vx)(o, l, {}),
                    eventTrigger: (0,
                    i.cT)(s, o, l)
                },
                l && l instanceof Object && 0 === Object.keys(l).length && (r.properties = void 0),
                l && "standard" === l.pixelMethod && delete r.properties,
                (0,
                i.tf)(p)) {
                    let e = {};
                    for (let t in c)
                        B.c1.indexOf(t) > -1 || ("object" == typeof c[t] ? Object.assign(e, c[t]) : e[t] = c[t]);
                    r.properties = e
                }
                let d = {
                    type: a.Event,
                    detail: r,
                    dedupeID: `${u}-${t}`
                };
                e.sendMessage(d)
            }
            )
        }
          , el = e => function() {
            for (var t = arguments.length, r = Array(t), s = 0; s < t; s++)
                r[s] = arguments[s];
            let n = {
                type: a.API,
                detail: {
                    name: "identify",
                    properties: r
                }
            };
            e.sendMessage(n)
        }
          , ec = e => function() {
            for (var t = arguments.length, r = Array(t), s = 0; s < t; s++)
                r[s] = arguments[s];
            let n = r[0];
            if (W(n)) {
                let t = {
                    type: a.PixelError,
                    detail: {
                        type: "duplicate_pixel_id",
                        pixelCode: n,
                        pixelName: ""
                    }
                };
                e.sendMessage(t)
            }
        }
          , eh = e => () => {
            let t = {
                type: a.SPA,
                detail: {
                    type: "SPA_Change",
                    timeStamp: Date.now()
                }
            };
            e.sendMessage(t);
            let r = b();
            r && r.forEach(t => {
                let r = {
                    type: a.Pixel,
                    detail: t
                };
                e.sendMessage(r)
            }
            )
        }
          , eu = e => t => {
            let r = t[B.Ny];
            r && e.sendMessage({
                type: a.FirstPartyCookie,
                detail: {
                    value: r,
                    expire: 0
                }
            })
        }
          , ed = e => () => {
            e.consentUpdateHandler()
        }
        ;
        ( () => {
            let e = new Y;
            B.Ic.test(window.location.href) && (window._tiktokHelperInstalled = !0);
            let t = ei(e)
              , r = eo(e)
              , a = ep(e)
              , s = el(e)
              , n = ec(e)
              , i = eh(e)
              , o = eu(e)
              , p = ed(e);
            C(o),
            g(i),
            m(t),
            O(r),
            M(a),
            F(p),
            j("identify", s),
            j("load", n),
            G(r)
        }
        )()
    }
    )()
}
)();
